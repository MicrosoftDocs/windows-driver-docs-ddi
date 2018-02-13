---
UID: NS:usb._USBD_PIPE_INFORMATION
title: "_USBD_PIPE_INFORMATION"
author: windows-driver-content
description: The USBD_PIPE_INFORMATION structure is used by USB client drivers to hold information about a pipe from a specific interface.
old-location: buses\usbd_pipe_information.htm
old-project: usbref
ms.assetid: 92e4e960-fd74-42e1-8448-a07676507427
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: USBD_PIPE_INFORMATION, usb/PUSBD_PIPE_INFORMATION, usbstrct_79d986fc-2853-4179-8a41-cc438582b317.xml, PUSBD_PIPE_INFORMATION, *PUSBD_PIPE_INFORMATION, usb/USBD_PIPE_INFORMATION, USBD_PIPE_INFORMATION structure [Buses], PUSBD_PIPE_INFORMATION structure pointer [Buses], _USBD_PIPE_INFORMATION, buses.usbd_pipe_information
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usb.h
apiname:
-	USBD_PIPE_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PUSBD_PIPE_INFORMATION, USBD_PIPE_INFORMATION"
req.product: Windows 10 or later.
---

# _USBD_PIPE_INFORMATION structure


## -description


The  <b>USBD_PIPE_INFORMATION</b> structure is used by USB client drivers to hold information about a pipe from a specific interface.


## -syntax


````
typedef struct _USBD_PIPE_INFORMATION {
  USHORT           MaximumPacketSize;
  UCHAR            EndpointAddress;
  UCHAR            Interval;
  USBD_PIPE_TYPE   PipeType;
  USBD_PIPE_HANDLE PipeHandle;
  ULONG            MaximumTransferSize;
  ULONG            PipeFlags;
} USBD_PIPE_INFORMATION, *PUSBD_PIPE_INFORMATION;
````


## -struct-fields




### -field MaximumPacketSize

Specifies the maximum packet size, in bytes, that this pipe handles. This value must be less than or equal to the value of <b>wMaxPacketSize</b> in the endpoint descriptor. The USB stack ignores this value if the USBD_PF_CHANGE_MAX_PACKET flag is not set in the <b>PipeFlags</b> member. 

For high-speed isochronous endpoints, the received <b>MaximumPacketSize</b> value includes the number of bytes that can be transferred in additional transactions, if the endpoint supports them. For more information, see Remarks.


### -field EndpointAddress

Specifies the bus address for this pipe.


### -field Interval

Contains the polling interval, indicated by the <b>bInterval</b> field in the corresponding endpoint descriptor (<a href="..\usbspec\ns-usbspec-_usb_endpoint_descriptor.md">USB_ENDPOINT_DESCRIPTOR</a>). This value is only valid for interrupt and isochronous pipes.  For other types of pipe, this value should be ignored. It reflects the device's configuration in firmware. Drivers cannot change it. 

The polling interval, together with the speed of the device and the type of host controller, determine the frequency with which the driver should initiate a transfer. The value in <b>Interval</b> does not represent a fixed amount of time. It is a relative value, and the actual polling frequency will also depend on whether the device and the USB host controller operate at low, full or high speed. 

If either the host controller or the device operates at low speed, the period of time between transfers (also known as the  "polling period") is measured in units of 1 millisecond frames, and the period is related to the value in <b>Interval</b> as indicated the following table:

<table>
<tr>
<th>Interval</th>
<th>Polling Period (1-millisecond frames)</th>
<th>Interrupt</th>
<th>Isochronous</th>
</tr>
<tr>
<td>0 to 15</td>
<td>8</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>16 to 35</td>
<td>16</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>36 to 255</td>
<td>32</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
</table>
 

For devices and host controllers that can operate at full speed, the period is measured in units of 1 millisecond frames. For full-speed isochronous transfers,  the <b>Interval</b> value and the  polling period is  always 1. That value indicates that data can be transferred in every frame. For full-speed interrupt transfers, the polling period is derived from the <b>Interval</b> value. The following table indicates the supported values for interrupt and isochronous endpoints.

<table>
<tr>
<th>Interval</th>
<th>Polling Period (1-millisecond frames)</th>
<th>Interrupt</th>
<th>Isochronous</th>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>2 to 3</td>
<td>2</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>4 to 7</td>
<td>4</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>8 to 15</td>
<td>8</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>16 to 31</td>
<td>16</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>32 to 255</td>
<td>32</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
</table>
 

For devices and host controllers that can operate at high speed, the period is measured in units of microframes. The polling period is derived from the <b>Interval</b> value by using the formula <code>Polling period = 2 ** (Interval - 1)</code>.  The calculated values are indicated in the following table:

<table>
<tr>
<th>Interval</th>
<th>Polling Period (microframes)</th>
<th>Interrupt  </th>
<th>Isochronous</th>
</tr>
<tr>
<td>1</td>
<td>1</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>2</td>
<td>2</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>3</td>
<td>4</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>4</td>
<td>8</td>
<td>Supported.</td>
<td>Supported.</td>
</tr>
<tr>
<td>5</td>
<td>16</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
<tr>
<td>6 to 255</td>
<td>32</td>
<td>Supported.</td>
<td>Not supported.</td>
</tr>
</table>
 

The supported polling periods for high-speed isochronous transfers are 1, 2, 4, and 8. If a client driver submits a URB_FUNCTION_ISOCH_TRANSFER request for a high speed isochronous endpoint with polling period greater than 8, the request fails with status USBD_STATUS_INVALID_PARAMETER. For  information about isochronous transfers, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>.

The mappings in the preceding tables between periods and polling intervals are valid in Microsoft Windows 2000 and later versions of the Windows operating system.


### -field PipeType

Specifies what type of transfers this pipe uses. These values are defined in the <a href="..\usb\ne-usb-_usbd_pipe_type.md">USBD_PIPE_TYPE</a> enumeration.


### -field PipeHandle

Specifies an opaque handle to the bulk or interrupt pipe. The host controller driver returns this handle when the client driver selects the device configuration with a URB of type URB_FUNCTION_SELECT_CONFIGURATION or when the client driver changes the settings for an interface with a URB of type URB_FUNCTION_SELECT_INTERFACE.    


### -field MaximumTransferSize

Specifies the maximum size, in bytes, for a transfer request on this pipe. In Windows Server 2003, Windows XP and later operating systems, this member is not used and does not contain valid data. 

For information about the maximum transfer sizes of each type of USB endpoint in different versions of Windows, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538112">USB Transfer and Packet Sizes</a>.

<div class="alert"><b>Note</b>  For WinUSB, do not use <b>MaximumTransferSize</b> to determine the maximum size of a USB transfer. Instead, use the MAXIMUM_TRANSFER_SIZE value retrieved by  <a href="https://msdn.microsoft.com/library/windows/hardware/ff540266">WinUsb_GetPipePolicy</a>.</div>
<div> </div>

### -field PipeFlags

Contains a bitwise-OR of pipe flags that the driver can use to specify certain configurable characteristics of the pipe. The driver specifies these pipe characteristics when it selects the configuration of a USB device with a URB request whose function type is URB_FUNCTION_SELECT_CONFIGURATION. 

The following table explains the meaning of each pipe flag: 

<table>
<tr>
<th>Flag name</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBD_PF_CHANGE_MAX_PACKET

</td>
<td>
Indicates that the driver is overriding the endpoint maximum packet size with the value specified in <b>MaximumPacketSize</b>. This value must be less than or equal to the default maximum specified in the pipe's endpoint descriptor. 

</td>
</tr>
</table>
 


## -remarks



This structure contains information for an endpoint, retrieved from the device's interface descriptor. For an explanation of how to obtain the information in <b>USBD_PIPE_INFORMATION</b> from the interface descriptor, see <a href="https://msdn.microsoft.com/library/windows/hardware/gg615081">How to Select a Configuration for a USB Device</a>. 

The <b>MaximumPacketSize</b> value  is derived from the first <b>11</b> bits of the <b>wMaxPacketSize</b> field of the endpoint descriptor, which indicates the maximum number of bytes that the host controller can send to or receive from the endpoint in a single transaction.

Typically, for high-speed transfers, the host controller sends or receives one transaction per microframe. However, high speed, high bandwidth isochronous or interrupt endpoints support higher data rates through additional transactions. This allows the host controller to transfer up to 3072 bytes in a single microframe. The number of additional transactions supported by that type of endpoint is indicated by bits <b>12..11</b> of <b>wMaxPacketSize</b> (least significant bit is 0). That number can be 0, 1, or 2. If <b>12..11</b> indicate 0, additional transactions per microframe are not supported by the endpoint. If the number is 1, then the host controller can send an additional transaction (total of two transactions per microframe); 2 indicates two additional transactions (total of three transactions per microframe).



The value received in <b>MaximumPacketSize</b> for an isochronous endpoint (high-speed and high-bandwidth) indicates the total number of bytes that the host controller can send to or receive from the endpoint in one microframe. The value includes the number of bytes in additional transactions, if the endpoint supports them. For example, consider the following isochronous endpoint characteristics: <ul>
<li><b>wMaxPacketSize</b> is 1,024</li>
<li>Bits <b>12..11</b> indicate 2</li>
<li><b>Interval</b> is 1.</li>
</ul>In the preceding example, the value received in <b>MaximumPacketSize</b> is 3,072 bytes  (Total transactions * <b>wMaxPacketSize</b>). Because <b>Interval</b> is 1, the polling period is 1. Thus, the host controller can transfer 3,072 bytes in each microframe of a frame. In a single I/O  request (described in one URB), the host controller can transfer no more than 24,576 bytes.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbspec\ns-usbspec-_usb_endpoint_descriptor.md">USB_ENDPOINT_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_PIPE_INFORMATION structure%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

