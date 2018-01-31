---
UID: NS:winspool.PrintPropertiesCollection
title: PrintPropertiesCollection
author: windows-driver-content
description: "."
old-location: print\printpropertiescollection.htm
old-project: print
ms.assetid: 824E8A5C-7530-4C7B-B093-386DD3D45A6B
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print.printpropertiescollection, winspool/PrintPropertiesCollection, PrintPropertiesCollection structure [Print Devices], PrintPropertiesCollection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winspool.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winspool.h
apiname:
-	PrintPropertiesCollection
product: Windows
targetos: Windows
req.typenames: PrintPropertiesCollection
req.product: Windows 10 or later.
---

# PrintPropertiesCollection structure


## -description





## -syntax


````
typedef struct {
  ULONG                    numberOfProperties;
  PrintNamedProperty       *propertiesCollection;
} PrintPropertiesCollection;
````


## -struct-fields




#### - numberOfProperties



#### - propertiesCollection


