---
UID: NF:swenum.KsGetBusEnumParentFDOFromChildPDO
title: KsGetBusEnumParentFDOFromChildPDO function
author: windows-driver-content
description: The KsGetBusEnumParentFDOFromChildPDO function retrieves the FDO of the parent of the given child PDO.
old-location: stream\ksgetbusenumparentfdofromchildpdo.htm
old-project: stream
ms.assetid: 5d860c5c-e29e-4ea2-b6f7-bcaab0d4584d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_592bfe23-7135-4118-9acf-6783691c55ea.xml, stream.ksgetbusenumparentfdofromchildpdo, KsGetBusEnumParentFDOFromChildPDO function [Streaming Media Devices], swenum/KsGetBusEnumParentFDOFromChildPDO, KsGetBusEnumParentFDOFromChildPDO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetBusEnumParentFDOFromChildPDO
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---

# KsGetBusEnumParentFDOFromChildPDO function


## -description


<i>This function is intended for internal use only.</i>

The <b>KsGetBusEnumParentFDOFromChildPDO </b>function retrieves the FDO of the parent of the given child PDO. 


## -syntax


````
NTSTATUS KsGetBusEnumParentFDOFromChildPDO(
  _In_  PDEVICE_OBJECT DeviceObject,
  _Out_ PDEVICE_OBJECT *FunctionalDeviceObject
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the child's PDO.


### -param FunctionalDeviceObject [out]

Pointer to the device object to receive the parent's FDO.


## -returns


Returns STATUS_SUCCESS if successful, or STATUS_INVALID_PARAMETER if <i>DeviceObject</i> does not contain a device extension, or if the device extension specified in <i>DeviceObject </i>is not that of a PDO.


