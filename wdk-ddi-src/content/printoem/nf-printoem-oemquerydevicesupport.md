---
UID: NF:printoem.OEMQueryDeviceSupport
title: OEMQueryDeviceSupport function
author: windows-driver-content
description: The OEMQueryDeviceSupport function returns requested device-specific information.
old-location: print\oemquerydevicesupport.htm
old-project: print
ms.assetid: 38e1bb07-be98-494b-a9c9-a83edef367e0
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMQueryDeviceSupport
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
req.alt-api: OEMQueryDeviceSupport
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

# OEMQueryDeviceSupport function



## -description
The <code>OEMQueryDeviceSupport</code> function returns requested device-specific information.



## -syntax

````
BOOL APIENTRY OEMQueryDeviceSupport(
        SURFOBJ                     *pso,
        XLATEOBJ                    *pxlo,
        XFORMOBJ                    *pxo,
        ULONG                       iType,
        ULONG                       cjIn,
  _In_  _reads_bytes_(cjIn) PVOID   pvIn,
        ULONG                       cjOut,
  _Out_ _writes_bytes_(cjOut) PVOID pvOut
);
````


## -parameters

### -param pso 


### -param pxlo 


### -param pxo 


### -param iType 


### -param cjIn 


### -param pvIn [in]


### -param cjOut 


### -param pvOut [out]


## -remarks
