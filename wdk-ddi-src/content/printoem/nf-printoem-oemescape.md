---
UID: NF:printoem.OEMEscape
title: OEMEscape function
author: windows-driver-content
description: The OEMEscape function retrieves information from a device that is not available in a device-independent device driver interface; the particular query depends on the value of the iEsc parameter.
old-location: print\oemescape.htm
old-project: print
ms.assetid: 3acc1c1f-5696-4297-a34e-047e402dbdcb
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMEscape
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
req.alt-api: OEMEscape
req.alt-loc: printoem.h
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
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMEscape function



## -description
The <code>OEMEscape</code> function retrieves information from a device that is not available in a device-independent device driver interface; the particular query depends on the value of the <i>iEsc</i> parameter.



## -syntax

````
ULONG APIENTRY OEMEscape(
        SURFOBJ                     *pso,
        ULONG                       iEsc,
        ULONG                       cjIn,
  _In_  _reads_bytes_(cjIn) PVOID   pvIn,
        ULONG                       cjOut,
  _Out_ _writes_bytes_(cjOut) PVOID pvOut
);
````


## -parameters

### -param pso 


### -param iEsc 


### -param cjIn 


### -param pvIn [in]


### -param cjOut 


### -param pvOut [out]


## -remarks
