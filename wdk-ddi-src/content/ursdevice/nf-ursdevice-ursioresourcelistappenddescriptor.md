---
UID: NF:ursdevice.UrsIoResourceListAppendDescriptor
title: UrsIoResourceListAppendDescriptor function (ursdevice.h)
description: Appends the specified resource descriptor to the specified I/O resource list object that maintains resource descriptors for the host or function role.
old-location: buses\ursioresourcelistappenddescriptor.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UrsIoResourceListAppendDescriptor function"]
ms.keywords: UrsIoResourceListAppendDescriptor, UrsIoResourceListAppendDescriptor function [Buses], buses.ursioresourcelistappenddescriptor, ursdevice/UrsIoResourceListAppendDescriptor
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Urscxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UrsIoResourceListAppendDescriptor
 - ursdevice/UrsIoResourceListAppendDescriptor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Urscxstub.lib
 - Urscxstub.dll
api_name:
 - UrsIoResourceListAppendDescriptor
---

# UrsIoResourceListAppendDescriptor function


## -description

Appends the specified resource descriptor to the specified I/O resource list object that maintains resource descriptors for the
    host or function role.

## -parameters

### -param IoResourceList [in]


 A role's I/O resource list object to which the resource descriptor is appended. This object is allocated by the framework and passed to the client driver when the framework invokes the driver's <a href="/windows-hardware/drivers/ddi/ursdevice/nc-ursdevice-evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> implementation.

### -param Descriptor [in]


A pointer to  IO_RESOURCE_DESCRIPTOR that contains the resource descriptor for the role.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.

## -remarks

After the client driver calls <a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a>, the framework allocates memory for the <i>resource requirements list</i>. When the USB dual-role class extension  invokes the client driver's implementation of <a href="/windows-hardware/drivers/ddi/ursdevice/nc-ursdevice-evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>, it passes a WDFIORESREQLIST handle to that requirements list along with URSIORESLIST handles for host and function role <i>resource lists</i>. In the implementation, the client driver is expected to enumerate through the requirements list and add the resource descriptor (if it wants to use that resource)  to the resource list for each role.

To add a resource descriptors for a role, the driver calls <b>UrsIoResourceListAppendDescriptor</b> and specifies the descriptor and the resource list to which the resource must be added. 

For a code example, see <a href="/windows-hardware/drivers/ddi/ursdevice/nc-ursdevice-evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>.

For more information about resource requirements lists, see <a href="/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Handling Hardware Resources</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ursdevice/nc-ursdevice-evt_urs_device_filter_resource_requirements">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a>



<a href="/windows-hardware/drivers/ddi/ursdevice/nf-ursdevice-ursdeviceinitialize">UrsDeviceInitialize</a>
