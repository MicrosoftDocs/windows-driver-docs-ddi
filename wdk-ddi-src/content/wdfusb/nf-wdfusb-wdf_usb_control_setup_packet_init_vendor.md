---
UID: NF:wdfusb.WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR
title: WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR function
author: windows-driver-content
description: The WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a vendor-specific USB control transfer.
old-location: wdf\wdf_usb_control_setup_packet_init_vendor.htm
old-project: wdf
ms.assetid: 58774dcf-f48c-4d39-acbe-fe09b4c52d81
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_e29c876f-b916-47a4-af86-2597c8ba3e21.xml, WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR, WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR function, kmdf.wdf_usb_control_setup_packet_init_vendor, wdf.wdf_usb_control_setup_packet_init_vendor, wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR
product: Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure for a vendor-specific USB control transfer.


## -parameters




### -param Packet [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Direction [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552545">WDF_USB_BMREQUEST_DIRECTION</a>-typed value that is stored in the <b>Packet.bm.Request.Dir</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Recipient [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552554">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value that is stored in the <b>Packet.bm.Request.Recipient</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Request [in]

A request type constant that is stored in the <b>Packet.bRequest</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Value [in]

A request-specific value that is stored in the <b>Packet.wValue.Value</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param Index [in]

A request-specific index value that is stored in the <b>Packet.wIndex.Value</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


## -returns



None




## -remarks



The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</b> function does the following:

<ul>
<li>
Zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

</li>
<li>
Sets the <b>Packet.bm.Request.Type</b> member to <b>BmRequestVendor</b>.

</li>
<li>
Sets other structure members by using the <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</b> function's input arguments.

</li>
</ul>
To initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure, the driver should call one of the following functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552571">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552574">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552576">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552582">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>


</li>
<li>
<b>WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</b>

</li>
</ul>
The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_CONTROL_SETUP_PACKET  controlSetupPacket;

WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR(
                                         &amp;controlSetupPacket,
                                         BmRequestHostToDevice,
                                         BmRequestToDevice,
                                         USBFX2LK_REENUMERATE,
                                         0,
                                         0
                                         );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552545">WDF_USB_BMREQUEST_DIRECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552554">WDF_USB_BMREQUEST_RECIPIENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552571">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552574">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552576">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552582">WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</a>
 

 

