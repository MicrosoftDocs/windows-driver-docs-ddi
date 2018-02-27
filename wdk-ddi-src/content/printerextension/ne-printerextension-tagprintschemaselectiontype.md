---
UID: NE:printerextension.tagPrintSchemaSelectionType
title: tagPrintSchemaSelectionType
author: windows-driver-content
description: The PrintSchemaSelectionType enumeration identifies how a Feature’s options should be selected. This property appears only in a PrintCapabilities document.
old-location: print\printschemaselectiontype.htm
old-project: print
ms.assetid: 30BB7A95-512C-418B-B496-47832DD4C0BC
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PrintSchemaSelectionType, PrintSchemaSelectionType enumeration [Print Devices], PrintSchemaSelectionType_PickMany, PrintSchemaSelectionType_PickOne, print.printschemaselectiontype, printerextension/PrintSchemaSelectionType, printerextension/PrintSchemaSelectionType_PickMany, printerextension/PrintSchemaSelectionType_PickOne, tagPrintSchemaSelectionType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Printerextension.h
api_name:
-	PrintSchemaSelectionType
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# tagPrintSchemaSelectionType enumeration


## -description


The PrintSchemaSelectionType enumeration identifies how a Feature’s options should be selected. This property appears only in a PrintCapabilities document. 


## -syntax


````
typedef enum tagPrintSchemaSelectionType { 
  PrintSchemaSelectionType_PickOne   = 0,
  PrintSchemaSelectionType_PickMany  = 1
} PrintSchemaSelectionType;
````


## -enum-fields




### -field PrintSchemaSelectionType_PickOne

Select one.


### -field PrintSchemaSelectionType_PickMany

Select many.

