---
UID: NS:wdfusb._WDF_USB_PIPE_INFORMATION
title: "_WDF_USB_PIPE_INFORMATION"
author: windows-driver-content
description: The WDF_USB_PIPE_INFORMATION structure contains information about a USB pipe and its endpoint.
old-location: wdf\wdf_usb_pipe_information.htm
old-project: wdf
ms.assetid: 05cba67b-c9da-4345-bc6f-09de12a617c1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_USB_PIPE_INFORMATION, DFUsbRef_80f26f29-adf0-4017-b261-36637da41c0d.xml, PWDF_USB_PIPE_INFORMATION, PWDF_USB_PIPE_INFORMATION structure pointer, WDF_USB_PIPE_INFORMATION, WDF_USB_PIPE_INFORMATION structure, _WDF_USB_PIPE_INFORMATION, kmdf.wdf_usb_pipe_information, wdf.wdf_usb_pipe_information, wdfusb/PWDF_USB_PIPE_INFORMATION, wdfusb/WDF_USB_PIPE_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Windows
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
-	WDF_USB_PIPE_INFORMATION
product: Windows
targetos: Windows
req.typenames: WDF_USB_PIPE_INFORMATION, *PWDF_USB_PIPE_INFORMATION
req.product: Windows 10 or later.
---

# _WDF_USB_PIPE_INFORMATION structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_PIPE_INFORMATION</b> structure contains information about a USB pipe and its endpoint.


## -syntax


````
typedef struct _WDF_USB_PIPE_INFORMATION {
  ULONG             Size;
  ULONG             MaximumPacketSize;
  UCHAR             EndpointAddress;
  UCHAR             Interval;
  UCHAR             SettingIndex;
  WDF_USB_PIPE_TYPE PipeType;
  ULONG             MaximumTransferSize;
} WDF_USB_PIPE_INFORMATION, *PWDF_USB_PIPE_INFORMATION;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field MaximumPacketSize

The maximum packet size, in bytes, that the pipe's endpoint is capable of sending or receiving.

For high-speed isochronous endpoints, the received <b>MaximumPacketSize</b> value includes the number of bytes that can be transferred in additional transactions, if the endpoint supports them.


### -field EndpointAddress

The address of the endpoint on the USB device. For more information about endpoint addresses, see the USB specification.


### -field Interval

The endpoint's polling interval, if the <b>PipeType</b> member is set to <b>WdfUsbPipeTypeInterrupt</b>. For more information about polling intervals, see the USB specification.


### -field SettingIndex

An index value that identifies the alternate setting, within an interface, that the pipe belongs to. For more information about alternate settings, see the USB specification.


### -field PipeType

A <a href="..\wdfusb\ne-wdfusb-_wdf_usb_pipe_type.md">WDF_USB_PIPE_TYPE</a>-typed value that specifies the type of pipe.


### -field MaximumTransferSize

This member is not used.  


## -remarks



The <b>WDF_USB_PIPE_INFORMATION</b> structure is filled in by the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipegetinformation.md">WdfUsbTargetPipeGetInformation</a>, <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>, and <a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetendpointinformation.md">WdfUsbInterfaceGetEndpointInformation</a> methods.

To initialize a <b>WDF_USB_PIPE_INFORMATION</b> structure, your driver should call <a href="..\wdfusb\nf-wdfusb-wdf_usb_pipe_information_init.md">WDF_USB_PIPE_INFORMATION_INIT</a>.

For more information about the <b>MaximumPacketSize</b> member of this structure, see  the Remarks section of <a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a>.

For information on how to transfer data to and from supported isochronous endpoints in a USB device, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>.




## -see-also

<a href="..\wdfusb\nf-wdfusb-wdf_usb_pipe_information_init.md">WDF_USB_PIPE_INFORMATION_INIT</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipegetinformation.md">WdfUsbTargetPipeGetInformation</a>



<a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetendpointinformation.md">WdfUsbInterfaceGetEndpointInformation</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbinterfacegetconfiguredpipe.md">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="..\wdfusb\ne-wdfusb-_wdf_usb_pipe_type.md">WDF_USB_PIPE_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_PIPE_INFORMATION structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

