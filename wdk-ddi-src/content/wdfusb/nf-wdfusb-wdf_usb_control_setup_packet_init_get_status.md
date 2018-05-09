---
UID: NF:wdfusb.WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS
title: WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function
author: windows-driver-content
description: The WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function initializes a WDF_USB_CONTROL_SETUP_PACKET structure for a USB control transfer that obtains device status.
old-location: wdf\wdf_usb_control_setup_packet_init_get_status.htm
old-project: wdf
ms.assetid: 1d21fe54-761b-42cf-9da2-83687cb9e079
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_b1eaf694-27f6-4767-9e7f-f9af5c0fd605.xml, WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS, WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function, kmdf.wdf_usb_control_setup_packet_init_get_status, wdf.wdf_usb_control_setup_packet_init_get_status, wdfusb/WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS
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
-	WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure for a USB control transfer that obtains device status.


## -parameters




### -param Packet [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


### -param BmRequestRecipient [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552554">WDF_USB_BMREQUEST_RECIPIENT</a>-typed value that is stored in the <b>Packet.bm.Request.Recipient</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure. 


### -param Index [in]

A status index value that is stored in the <b>Packet.wIndex.Value</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.


## -returns



None




## -remarks



The <b>WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</b> function does the following:

<ol>
<li>
Zeros the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

</li>
<li>
Sets the <b>Packet.bm.Request.Type</b> member to <b>BmRequestStandard</b>.

</li>
<li>
Sets the <b>Packet.bm.Request.Dir</b> member to <b>BmRequestDeviceToHost</b>.

</li>
<li>
Sets the <b>Packet.bRequest</b> member to a "get status" request value.

</li>
<li>
Sets the <b>Packet.wValue.Value</b> member to zero.

</li>
<li>
Sets the <b>Packet-&gt;Packet.wIndex.Value</b> member to the <i>Index</i> argument.

</li>
</ol>
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
<b>WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS</b>

</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552588">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>


</li>
</ul>

#### Examples

The following code example  initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_USB_CONTROL_SETUP_PACKET  packet;

WDF_USB_CONTROL_SETUP_PACKET_INIT_GET_STATUS(
                                             &amp;packet,
                                             BmRequestToDevice,
                                             0
                                             );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552554">WDF_USB_BMREQUEST_RECIPIENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552571">WDF_USB_CONTROL_SETUP_PACKET_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552574">WDF_USB_CONTROL_SETUP_PACKET_INIT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552576">WDF_USB_CONTROL_SETUP_PACKET_INIT_FEATURE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552588">WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR</a>
 

 

