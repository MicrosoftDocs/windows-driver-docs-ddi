---
UID: NF:wdfdevice.WdfDeviceGetAlignmentRequirement
title: WdfDeviceGetAlignmentRequirement function (wdfdevice.h)
description: The WdfDeviceGetAlignmentRequirement method retrieves a device's address alignment requirement for memory transfer operations.
old-location: wdf\wdfdevicegetalignmentrequirement.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDeviceGetAlignmentRequirement function"]
ms.keywords: DFDeviceObjectGeneralRef_c7135427-9887-44e5-8380-28ebef4174a9.xml, WdfDeviceGetAlignmentRequirement, WdfDeviceGetAlignmentRequirement method, kmdf.wdfdevicegetalignmentrequirement, wdf.wdfdevicegetalignmentrequirement, wdfdevice/WdfDeviceGetAlignmentRequirement
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceGetAlignmentRequirement
 - wdfdevice/WdfDeviceGetAlignmentRequirement
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDeviceGetAlignmentRequirement
---

# WdfDeviceGetAlignmentRequirement function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceGetAlignmentRequirement</b> method retrieves a device's address alignment requirement for memory transfer operations.

## -parameters

### -param Device [in]


A handle to a framework device object.

## -returns

<b>WdfDeviceGetAlignmentRequirement</b> returns the device's current alignment requirement. This value is one of the FILE_<i>XXXX</i>_ALIGNMENT constants that are defined in <i>wdm.h</i>.

A bug check occurs if the driver supplies an invalid object handle.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetalignmentrequirement">WdfDeviceSetAlignmentRequirement</a>
