---
UID: NF:printoem.OEMDeviceCapabilities
title: OEMDeviceCapabilities function
author: windows-driver-content
description: OEMDeviceCapabilities function
old-location: print\oemdevicecapabilities.htm
old-project: print
ms.assetid: fb15fd82-6214-40c0-9982-faee6c6b35b3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMDeviceCapabilities
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
req.alt-api: OEMDeviceCapabilities
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

# OEMDeviceCapabilities function



## -description

## -syntax

````
DWORD APIENTRY OEMDeviceCapabilities(
   POEMUIOBJ poemuiobj,
   HANDLE    hPrinter,
   PWSTR     pDeviceName,
   WORD      wCapability,
   PVOID     pOutput,
   PDEVMODE  pPublicDM,
   PVOID     pOEMDM,
   DWORD     dwLastResult
);
````


## -parameters

### -param poemuiobj 


### -param hPrinter 


### -param pDeviceName 


### -param wCapability 


### -param pOutput 


### -param pPublicDM 


### -param pOEMDM 


### -param dwLastResult 


## -remarks
