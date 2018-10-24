---
UID: NF:poscx.PosCxGetDeviceInterfaceTag
title: PosCxGetDeviceInterfaceTag function
author: windows-driver-content
description: PosCxGetDeviceInterfaceTag returns the device interface tag that is set in PosCxOpen.
old-location: pos\poscxgetdeviceinterfacetag.htm
tech.root: pos
ms.assetid: CF54D922-8EEE-41CE-8CFC-0628756117BE
ms.date: 02/23/2018
ms.keywords: PosCxGetDeviceInterfaceTag, PosCxGetDeviceInterfaceTag function, pos.poscxgetdeviceinterfacetag, poscx/PosCxGetDeviceInterfaceTag
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	poscx.h
api_name:
-	PosCxGetDeviceInterfaceTag
product:
- Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# PosCxGetDeviceInterfaceTag function


## -description


PosCxGetDeviceInterfaceTag returns the device interface tag that is set in <a href="https://msdn.microsoft.com/library/windows/hardware/mt593129">PosCxOpen</a>.


## -parameters




### -param fileObject [in]

      A handle to a framework file object that identifies the caller, usually acquired with <a href="https://msdn.microsoft.com/library/windows/hardware/ff549963">WdfRequestGetFileObject</a>.


## -returns



      The device interface tag value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt593129">PosCxOpen</a>
 

 

