---
UID: NF:usbdlib.USBD_SelectInterfaceUrbAllocateAndBuild
title: USBD_SelectInterfaceUrbAllocateAndBuild function
author: windows-driver-content
description: The USBD_SelectInterfaceUrbAllocateAndBuild routine allocates and formats a URB structure that is required for a request to select an interface or change its alternate setting.
old-location: buses\usbd_selectinterfaceurballocateandbuild.htm
old-project: usbref
ms.assetid: D0B2E7EA-3D1F-4FD1-AB8D-EAB8406B9127
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBD_SelectInterfaceUrbAllocateAndBuild, USBD_SelectInterfaceUrbAllocateAndBuild routine [Buses], buses.usbd_selectinterfaceurballocateandbuild, usbdlib/USBD_SelectInterfaceUrbAllocateAndBuild
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbdex.lib
-	Usbdex.dll
api_name:
-	USBD_SelectInterfaceUrbAllocateAndBuild
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_SelectInterfaceUrbAllocateAndBuild function


## -description


The <b>USBD_SelectInterfaceUrbAllocateAndBuild</b> routine allocates and formats a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure that is required for a request to select an interface or change its alternate setting.




## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a> routine.


### -param ConfigurationHandle [in]

Handle returned by the USB driver stack in the  <b>UrbSelectConfiguration.ConfigurationHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure, after the driver stack completes a select-configuration  request.


### -param InterfaceListEntry

TBD


### -param Urb [out]

Pointer to a  <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure that receives the URB allocated by <b>USBD_SelectInterfaceUrbAllocateAndBuild</b>. The client driver must free the URB when the driver has finished using it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh406252">USBD_UrbFree</a>.


#### - InterfaceList [in]

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff539076">USBD_INTERFACE_LIST_ENTRY</a>    structure. For more information, see Remarks.


## -returns



The routine returns an NTSTATUS code. Possible  values include but are not limited to, the status codes listed in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine call succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller passed NULL in any of the parameters.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory available to complete the call.


</td>
</tr>
</table>
 




## -remarks



The client driver must call the <b>USBD_SelectInterfaceUrbAllocateAndBuild</b> routine after selecting a configuration in the device. After a select-configuration request completes, the client driver receives a configuration handle in the <b>UrbSelectConfiguration.ConfigurationHandle</b> member of the URB. That handle must be specified in the <i>ConfigurationHandle</i> parameter of <b>USBD_SelectInterfaceUrbAllocateAndBuild</b>. 

A client driver calls <b>USBD_SelectInterfaceUrbAllocateAndBuild</b> to allocate and build an URB for a select-interface request to change the alternate setting of an interface, in the selected configuration.  In the call to <b>USBD_SelectInterfaceUrbAllocateAndBuild</b>, the client driver must allocate and provide a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539076">USBD_INTERFACE_LIST_ENTRY</a> structure. The client driver must set the structure members as follows: 

<ul>
<li>The <b>InterfaceDescriptor</b> member must point to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> structure that contains the interface descriptor with the alternate setting to select. The interface descriptor was obtained in a previous request to get a configuration descriptor and the associated interface and endpoint descriptors. </li>
<li>The <b>Interface</b> member must be NULL.</li>
</ul>
<b>USBD_SelectInterfaceUrbAllocateAndBuild</b> allocates an <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure and fills it with information about the specified interface setting, and endpoints. The routine also allocates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure.  The structure members (except pipe information) are filled based on the specified interface descriptor. 
<b>USBD_SelectInterfaceUrbAllocateAndBuild</b> sets the <b>Interface</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539076">USBD_INTERFACE_LIST_ENTRY</a> to the address of <b>USBD_INTERFACE_INFORMATION</b> in the URB. The client driver can send this URB to the USB driver stack to select an alternate setting in the interface.

A client driver cannot change alternate settings in multiple interfaces in a single select-interface request. Each request targets only one interface.

After the select-interface request is complete, the USB driver stack populates <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> with information about pipes opened for endpoints that are defined in the selected alternate setting. The client driver can obtain those pipe handles by inspecting the  array pointed to by the <b>Pipes</b> member of <b>USBD_INTERFACE_INFORMATION</b>, and store the handles for future  data transfer requests.  

The client driver can reuse an URB allocated by <b>USBD_SelectInterfaceUrbAllocateAndBuild</b><i> only</i> for another select-interface request for the same alternate setting.  The client driver <i>must not</i> reuse the URB for any other type of request, or for another select-interface request for a different alternate setting.  Instead of allocating a new URB, reusing an existing URB  is the preferred approach in certain scenarios. Consider a USB audio device that has an interface with two alternate settings, defined for two bandwidth requirements. Setting 0 is defined  for zero bandwidth;  Setting 1 is defined to use a certain amount of bandwidth. The client driver wants to frequently switch between the two settings depending on whether the device is in use. To implement this scenario, the client driver can allocate two URBs for select-interface requests, one per setting. The client driver can use (and reuse) an URB for a select-interface request to select Setting 1 when there are sounds to send to the device. To conserve bandwidth when there are no sounds, the client driver can use (and reuse) the other URB to switch to Setting 0. This implementation prevents the client driver from allocating URBs for each of those select-interface requests, every time the driver needs to change the setting. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406243">USBD_SelectConfigUrbAllocateAndBuild</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_SelectInterfaceUrbAllocateAndBuild routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

