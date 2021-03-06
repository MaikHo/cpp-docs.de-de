---
title: Verwenden überprüfbarer Assemblys mit SQL Server (C++/CLI)
ms.date: 10/17/2018
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
ms.openlocfilehash: 27dec67cc0932a784cdd041ba346bb8c635b280d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384412"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>Verwenden überprüfbarer Assemblys mit SQL Server (C++/CLI)

Erweiterte gespeicherte Prozeduren, die als Dynamic Link Libraries (DLLs), bieten Sie eine Möglichkeit zum Erweitern der Funktionalität von SQL Server über Funktionen, die mit Visual C++ entwickelt wurden. Erweiterte gespeicherte Prozeduren werden als Funktionen in DLLs implementiert. Zusätzlich zu Funktionen, erweiterte gespeicherte Prozeduren können auch definieren [-benutzerdefinierte Typen](../cpp/classes-and-structs-cpp.md) und Aggregatfunktionen (z. B. SUM oder AVG).

Wenn ein Client eine erweiterte gespeicherte Prozedur ausgeführt wird, sucht SQL Server für die DLL der erweiterten gespeicherten Prozedur zugeordnet, und lädt die DLL. SQL Server die angeforderte erweiterte gespeicherte Prozedur aufruft und in einem angegebenen Sicherheitskontext ausgeführt. Die erweiterte gespeicherte Prozedur, und klicken Sie dann übergibt Ergebnis und Parameter an den Server gibt.

SQL Server bietet Erweiterungen in Transact-SQL (T-SQL), damit Sie überprüfbare Assemblys in SQL Server installieren können. Der SQL Server-Berechtigungssatz gibt den Sicherheitskontext, mit den folgenden Ebenen der Sicherheit:

- Uneingeschränkten Modus: Führen Sie Code auf eigenes Risiko; Code muss nicht überprüfbar typsicher sein.

- Im abgesicherten Modus: Führen Sie überprüfbar typsicheren Code; mit/clr: safe kompiliert.

> [!IMPORTANT]
> Visual Studio 2015 als veraltet markiert und Visual Studio 2017 nicht unterstützt. die **/CLR: pure** und **/CLR: safe** überprüfbare Projekte. Wenn Sie die überprüfbaren Code benötigen, empfehlen wir, dass Sie Ihren Code in c# übersetzen.

Verwenden Sie zum Erstellen und Laden eine überprüfbare Assembly in SQL Server, die Transact-SQL-Befehle erstellen und die DROP ASSEMBLY wie folgt:

```sql
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH
  PERMISSION_SET <permissions>
DROP ASSEMBLY <assemblyName>
```

Die PERMISSION_SET-Befehl gibt den Sicherheitskontext und kann die Werte nicht eingeschränkt, SAFE oder erweiterte aufweisen.

Darüber hinaus können Sie den Befehl CREATE FUNCTION, zum Binden an Methodennamen in einer Klasse:

```sql
CREATE FUNCTION <FunctionName>(<FunctionParams>)
RETURNS returnType
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]
```

## <a name="example"></a>Beispiel

Die folgende SQL-Skript (z. B. benannte "MyScript.sql"), lädt eine Assembly in SQL Server und stellt eine Methode einer Klasse zur Verfügung:

```sql
-- Create assembly without external access
drop assembly stockNoEA
go
create assembly stockNoEA
from
'c:\stockNoEA.dll'
with permission_set safe

-- Create function on assembly with no external access
drop function GetQuoteNoEA
go
create function GetQuoteNoEA(@sym nvarchar(10))
returns real
external name stockNoEA:StockQuotes::GetQuote
go

-- To call the function
select dbo.GetQuoteNoEA('MSFT')
go
```

SQL-Skripts können in SQL Query Analyzer oder in der Befehlszeile mit dem Hilfsprogramm sqlcmd.exe interaktiv ausgeführt werden. Die folgende Befehlszeile eine Verbindung mit "myserver", wird die Standarddatenbank verwendet, verwendet eine vertrauenswürdige Verbindung, MyScript.sql Eingaben und Ausgaben MyResult.txt.

```cmd
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt
```

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)
