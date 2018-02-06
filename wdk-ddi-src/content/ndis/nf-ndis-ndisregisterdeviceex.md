---
UID: NF:ndis.NdisRegisterDeviceEx
title: NdisRegisterDeviceEx function
author: windows-driver-content
description: The NdisRegisterDeviceEx function creates a device object that is based upon the specified attributes.
old-location: netvista\ndisregisterdeviceex.htm
old-project: netvista
ms.assetid: 8e0d406e-748c-4b37-90fb-c7b9dfc28362
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisRegisterDeviceEx, ndis_devices_ref_57ed58e5-f149-4cbe-ad9d-667f433a7e77.xml, ndis/NdisRegisterDeviceEx, netvista.ndisregisterdeviceex, NdisRegisterDeviceEx function [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisRegisterDeviceEx
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisRegisterDeviceEx function


## -description


The 
  <b>NdisRegisterDeviceEx</b> function creates a device object that is based upon the specified
  attributes.


## -syntax


````
NDIS_STATUS NdisRegisterDeviceEx(
  _In_  NDIS_HANDLE                    NdisHandle,
  _In_  PNDIS_DEVICE_OBJECT_ATTRIBUTES DeviceObjectAttributes,
  _Out_ PDEVICE_OBJECT                 *pDeviceObject,
  _Out_ PNDIS_HANDLE                   NdisDeviceHandle
);
````


## -parameters




### -param NdisHandle [in]

A miniport driver handle or filter driver handle that the caller obtained by calling the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function or the 
     <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
     NdisFRegisterFilterDriver</a> function respectively.


### -param DeviceObjectAttributes [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_device_object_attributes.md">
     NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure that contains the attributes for the new device.


### -param pDeviceObject [out]

A pointer that points to a pointer to a newly created 
     <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure, if the call succeeds.
     If the call fails, 
     <i>pDeviceObject</i> is set to point to <b>NULL</b>.


### -param NdisDeviceHandle [out]

A pointer to a caller-supplied variable in which this function, if it succeeds, returns a handle
     to the device object. This handle is a required parameter to the 
     <a href="..\ndis\nf-ndis-ndisderegisterdeviceex.md">NdisDeregisterDeviceEx</a> function
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
    <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that 
    <b>NdisRegisterDeviceEx</b> created.</div><div> </div>If an NDIS driver requires space for context information in the device object, the driver can pass a
    nonzero value for the 
    <b>ExtensionSize</b> member in the 
    <a href="..\ndis\ns-ndis-_ndis_device_object_attributes.md">
    NDIS_DEVICE_OBJECT_ATTRIBUTES</a> structure at the 
    <i>DeviceObjectAttributes</i> parameter. In this case, NDIS allocates the extension for the driver, and
    the driver can call the 
    <a href="..\ndis\nf-ndis-ndisgetdevicereservedextension.md">
    NdisGetDeviceReservedExtension</a> function to get a pointer to the extension.

The driver must subsequently call the 
    <a href="..\ndis\nf-ndis-ndisderegisterdeviceex.md">NdisDeregisterDeviceEx</a> function
    when the device is no longer needed. If 
    <b>NdisRegisterDeviceEx</b> allocated an extension, 
    <b>NdisDeregisterDeviceEx</b> frees the extension.



## -see-also

<a href="..\ndis\nf-ndis-ndisderegisterdeviceex.md">NdisDeregisterDeviceEx</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nf-ndis-ndisgetdevicereservedextension.md">
   NdisGetDeviceReservedExtension</a>

<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>

<a href="..\ndis\ns-ndis-_ndis_device_object_attributes.md">NDIS_DEVICE_OBJECT_ATTRIBUTES</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRegisterDeviceEx function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

