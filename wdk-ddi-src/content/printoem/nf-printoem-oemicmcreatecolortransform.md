---
UID: NF:printoem.OEMIcmCreateColorTransform
title: OEMIcmCreateColorTransform function
author: windows-driver-content
description: The OEMIcmCreateColorTransform function creates an ICM color transform.
old-location: print\oemicmcreatecolortransform.htm
old-project: print
ms.assetid: 995fdac4-e958-4eed-ba3a-7be0349dec59
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.oemicmcreatecolortransform, print_unidrv-pscript_rendering_102b853d-78f9-4e06-a3e5-c76f55caa42e.xml, OEMIcmCreateColorTransform, OEMIcmCreateColorTransform function [Print Devices], printoem/OEMIcmCreateColorTransform
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
-	OEMIcmCreateColorTransform
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMIcmCreateColorTransform function


## -description


The <code>OEMIcmCreateColorTransform</code> function creates an ICM color transform.


## -syntax


````
HANDLE APIENTRY OEMIcmCreateColorTransform(
           DHPDEV                                   dhpdev,
           LPLOGCOLORSPACEW                         pLogColorSpace,
  _In_opt_ _reads_bytes_(cjSourceProfile) PVOID     pvSourceProfile,
           ULONG                                    cjSourceProfile,
  _In_     _reads_bytes_(cjDestProfile) PVOID       pvDestProfile,
           ULONG                                    cjDestProfile,
  _In_opt_ _reads_bytes_opt_(cjTargetProfile) PVOID pvTargetProfile,
           ULONG                                    cjTargetProfile,
           POINTL                                   dwReserved
);
````


## -parameters




### -param dhpdev


### -param pLogColorSpace


### -param pvSourceProfile [in, optional]


### -param cjSourceProfile


### -param pvDestProfile [in]


### -param cjDestProfile


### -param pvTargetProfile [in, optional]


### -param cjTargetProfile


### -param dwReserved

