---
UID: NF:ndis.NdisRegisterDeviceEx
title: NdisRegisterDeviceEx function (ndis.h)
description: The NdisRegisterDeviceEx function creates a device object that is based upon the specified attributes.
old-location: netvista\ndisregisterdeviceex.htm
tech.root: netvista
ms.assetid: 8e0d406e-748c-4b37-90fb-c7b9dfc28362
ms.date: 05/02/2018
keywords: ["NdisRegisterDeviceEx function"]
ms.keywords: NdisRegisterDeviceEx, NdisRegisterDeviceEx function [Network Drivers Starting with Windows Vista], ndis/NdisRegisterDeviceEx, ndis_devices_ref_57ed58e5-f149-4cbe-ad9d-667f433a7e77.xml, netvista.ndisregisterdeviceex
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisRegisterDeviceEx
 - ndis/NdisRegisterDeviceEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisRegisterDeviceEx
---

# NdisRegisterDeviceEx function


## -description

The 
  <b>NdisRegisterDeviceEx</b> function creates a device object that is based upon the specified
  attributes.

## -parameters

### -param NdisHandle 

[in]
A miniport driver handle or filter driver handle that the caller obtained by calling the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
     NdisMRegisterMiniportDriver</a> function or the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">
     NdisFRegisterFilterDriver</a> function respectively.

### -param DeviceObjectAttributes 

[in]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_device_object_attributes">
     NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure that contains the attributes for the new device.

### -param pDeviceObject 

[out]
A pointer that points to a pointer to a newly created 
     <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure, if the call succeeds.
     If the call fails, 
     <i>pDeviceObject</i> is set to point to <b>NULL</b>.

### -param NdisDeviceHandle 

[out]
A pointer to a caller-supplied variable in which this function, if it succeeds, returns a handle
     to the device object. This handle is a required parameter to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisderegisterdeviceex">NdisDeregisterDeviceEx</a> function
     that the driver calls subsequently.

## -returns

<b>NdisRegisterDeviceEx</b> returns one of the following status values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisRegisterDeviceEx</b> successfully registered the device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The caller is not an NDIS driver.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i> or NTSTATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The driver's attempt to register the device failed. Usually, such an error status is propagated
       from an 
       <b>Ndis<i>Xxx</i></b> function or a kernel-mode support routine.

</td>
</tr>
</table>

## -remarks

Miniport drivers and filter drivers can call 
    <b>NdisRegisterDeviceEx</b> to register a virtual device.

<div class="alert"><b>Note</b>  NDIS drivers must not modify the 
    <b>DeviceExtension</b> member of the 
    <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that 
    <b>NdisRegisterDeviceEx</b> created.</div>
<div> </div>
If an NDIS driver requires space for context information in the device object, the driver can pass a
    nonzero value for the 
    <b>ExtensionSize</b> member in the 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_device_object_attributes">
    NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure at the 
    <i>DeviceObjectAttributes</i> parameter. In this case, NDIS allocates the extension for the driver, and
    the driver can call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetdevicereservedextension">
    NdisGetDeviceReservedExtension</a> function to get a pointer to the extension.

The driver must subsequently call the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisderegisterdeviceex">NdisDeregisterDeviceEx</a> function
    when the device is no longer needed. If 
    <b>NdisRegisterDeviceEx</b> allocated an extension, 
    <b>NdisDeregisterDeviceEx</b> frees the extension.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_device_object_attributes">NDIS_DEVICE_OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisderegisterdeviceex">NdisDeregisterDeviceEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfregisterfilterdriver">NdisFRegisterFilterDriver</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisgetdevicereservedextension">
   NdisGetDeviceReservedExtension</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>