---
UID: NF:printoem.OEMIcmDeleteColorTransform
title: OEMIcmDeleteColorTransform function
author: windows-driver-content
description: The OEMIcmDeleteColorTransform function deletes the specified color transform.
old-location: print\oemicmdeletecolortransform.htm
old-project: print
ms.assetid: 820d9e28-fe06-4aa7-91d8-a90340affb94
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.oemicmdeletecolortransform, print_unidrv-pscript_rendering_bbbce51d-2346-4260-ae70-598d38276d69.xml, OEMIcmDeleteColorTransform function [Print Devices], printoem/OEMIcmDeleteColorTransform, OEMIcmDeleteColorTransform
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMIcmDeleteColorTransform
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMIcmDeleteColorTransform function


## -description


The <code>OEMIcmDeleteColorTransform</code> function deletes the specified color transform.


## -syntax


````
BOOL APIENTRY OEMIcmDeleteColorTransform(
   DHPDEV dhpdev,
   HANDLE hcmXform
);
````


## -parameters




### -param dhpdev


### -param hcmXform

