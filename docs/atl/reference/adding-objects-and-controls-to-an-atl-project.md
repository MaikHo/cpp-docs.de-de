---
title: Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt
ms.date: 05/09/2019
f1_keywords:
- vc.appwiz.ATL.controls
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
ms.openlocfilehash: b1bf4f85ccf7a0bb2d77bfb96c512349f581f193
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832450"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt

> [!NOTE]
> Der ATL COM+ 1.0 Komponenten-Assistent, der ATL-OLE DB-Consumer-Assistent und der ATL-Assistent für Active Server Page-Komponenten sind in Visual Studio 2019 und höher nicht verfügbar.

Sie können einen der ATL-Code-Assistenten verwenden, um Objekte oder Steuerelemente zu ATL. oder MFC-basierten Projekten hinzuzufügen. Für jedes COM-Objekt oder -Steuerelement, das Sie hinzufügen, generiert der Assistent CPP- und .h-Dateien sowie eine RGS-Datei für skriptbasierte Registrierungsunterstützung. Die folgenden ATL-Code-Assistenten sind in Visual Studio verfügbar:

- [ATL Simple Object (Einfaches ATL-Objekt)](../../atl/reference/atl-simple-object-wizard.md)
- [ATL-Dialogfeld](../../atl/reference/atl-dialog-wizard.md)
- [ATL-Steuerelement](../../atl/reference/atl-control-wizard.md)
- [ATL-Eigenschaftenseite](../../atl/reference/atl-property-page-wizard.md)
- [ATL Active Server Page-Komponente](../../atl/reference/atl-active-server-page-component-wizard.md)
- [ATL-OLE DB-Consumer](../../atl/reference/atl-ole-db-consumer-wizard.md)
- [ATL-Unterstützung zu MFC hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)
- [ATL COM+ 1.0 Komponenten-Assistent](../../atl/reference/atl-com-plus-1-0-component-wizard.md)
- [ATL-OLE DB-Anbieter](../../atl/reference/atl-ole-db-provider-wizard.md)

> [!NOTE]
> Bevor Sie ein ATL-Objekt zu Ihrem Projekt hinzufügen, sollten Sie die Details und Anforderungen für das Objekt in dessen zugehörigen Hilfethemen lesen.

## <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>Hinzufügen eines Objekts oder Steuerelements mit dem ATL-Steuerelement-Assistenten

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektknoten, und klicken Sie im Kontextmenü auf **Hinzufügen**. Klicken Sie auf **Klasse hinzufügen**.

   Das Dialogfeld [Klasse hinzufügen](../../ide/add-class-dialog-box.md) wird angezeigt.

1. Wählen Sie im Bereich **Kategorien** den Ordner **ATL** aus, und wählen Sie im Bereich **Vorlagen** das Objekt aus, das eingefügt werden soll. Klicken Sie auf **Öffnen**. Der Code-Assistent für das ausgewählte Objekt wird angezeigt.

   > [!NOTE]
   > Wenn Sie ein ATL-Objekt zu einem MFC-Projekt hinzufügen möchten, müssen Sie dem vorhandenen Projekt ATL-Unterstützung hinzufügen. Gehen Sie dazu entsprechend den Anweisungen vor, die in [Hinzufügen von ATL-Unterstützung zu einem MFC-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) aufgeführt sind.

   Wenn Sie versuchen, ein ATL-Objekt zu Ihrem MFC-Projekt hinzuzufügen, ohne vorher ATL-Unterstützung hinzugefügt zu haben, werden Sie alternativ von Visual Studio aufgefordert anzugeben, ob ATL-Unterstützung zu Ihrem Projekt hinzugefügt werden soll. Klicken Sie auf **Ja**, um ATL-Unterstützung zum Projekt hinzuzufügen und den ausgewählten ATL-Assistenten zu öffnen.

## <a name="see-also"></a>Weitere Informationen

[ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)<br/>
[C++-Projektvorlagen](../../build/reference/visual-cpp-project-types.md)<br/>
[Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Programmieren mit ATL-und C-Lauf Zeit Code](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Standardmäßige ATL-Projekt Konfigurationen](../../atl/reference/default-atl-project-configurations.md)
