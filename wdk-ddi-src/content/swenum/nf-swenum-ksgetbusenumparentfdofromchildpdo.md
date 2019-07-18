---
UID: NF:swenum.KsGetBusEnumParentFDOFromChildPDO
title: KsGetBusEnumParentFDOFromChildPDO function (swenum.h)
description: The KsGetBusEnumParentFDOFromChildPDO function retrieves the FDO of the parent of the given child PDO.
old-location: stream\ksgetbusenumparentfdofromchildpdo.htm
tech.root: stream
ms.assetid: 5d860c5c-e29e-4ea2-b6f7-bcaab0d4584d
ms.date: 04/23/2018
ms.keywords: KsGetBusEnumParentFDOFromChildPDO, KsGetBusEnumParentFDOFromChildPDO function [Streaming Media Devices], ksfunc_592bfe23-7135-4118-9acf-6783691c55ea.xml, stream.ksgetbusenumparentfdofromchildpdo, swenum/KsGetBusEnumParentFDOFromChildPDO
ms.topic: function
f1_keywords:
 - "swenum/KsGetBusEnumParentFDOFromChildPDO"
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsGetBusEnumParentFDOFromChildPDO
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetBusEnumParentFDOFromChildPDO function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsGetBusEnumParentFDOFromChildPDO </b>function retrieves the FDO of the parent of the given child PDO. 


## -parameters




### -param DeviceObject [in]

Pointer to the child's PDO.


### -param FunctionalDeviceObject [out]

Pointer to the device object to receive the parent's FDO.


## -returns



Returns STATUS_SUCCESS if successful, or STATUS_INVALID_PARAMETER if <i>DeviceObject</i> does not contain a device extension, or if the device extension specified in <i>DeviceObject </i>is not that of a PDO.



