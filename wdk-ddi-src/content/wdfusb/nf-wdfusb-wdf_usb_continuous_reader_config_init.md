---
UID: NF:wdfusb.WDF_USB_CONTINUOUS_READER_CONFIG_INIT
title: WDF_USB_CONTINUOUS_READER_CONFIG_INIT function
author: windows-driver-content
description: The WDF_USB_CONTINUOUS_READER_CONFIG_INIT function initializes a WDF_USB_CONTINUOUS_READER_CONFIG structure.
old-location: wdf\wdf_usb_continuous_reader_config_init.htm
old-project: wdf
ms.assetid: d9bf6c47-b7ce-413d-8871-4d9d68e27715
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_USB_CONTINUOUS_READER_CONFIG_INIT function, kmdf.wdf_usb_continuous_reader_config_init, wdfusb/WDF_USB_CONTINUOUS_READER_CONFIG_INIT, WDF_USB_CONTINUOUS_READER_CONFIG_INIT, DFUsbRef_a179cacd-e450-4a53-93e7-4eb3a59fc605.xml, wdf.wdf_usb_continuous_reader_config_init
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfusb.h
apiname:
-	WDF_USB_CONTINUOUS_READER_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# WDF_USB_CONTINUOUS_READER_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b> function initializes a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_continuous_reader_config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. 


## -syntax


````
VOID WDF_USB_CONTINUOUS_READER_CONFIG_INIT(
  _Out_ PWDF_USB_CONTINUOUS_READER_CONFIG     Config,
  _In_  PFN_WDF_USB_READER_COMPLETION_ROUTINE EvtUsbTargetPipeReadComplete,
  _In_  WDFCONTEXT                            EvtUsbTargetPipeReadCompleteContext,
  _In_  size_t                                TransferLength
);
````


## -parameters




### -param Config [out]

A pointer to a <a href="..\wdfusb\ns-wdfusb-_wdf_usb_continuous_reader_config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.


### -param EvtUsbTargetPipeReadComplete [in]

A pointer to the driver's <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a> callback function.


### -param EvtUsbTargetPipeReadCompleteContext [in]

An untyped pointer to driver-defined context information that the framework passes to the driver's <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a> callback function.


### -param TransferLength [in]

The maximum length, in bytes, of data that can be received from the device.


## -returns



None




## -remarks



The <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b> function zeros the specified <a href="..\wdfusb\ns-wdfusb-_wdf_usb_continuous_reader_config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>EvtUsbTargetPipeReadComplete</b>, <b>EvtUsbTargetPipeReadCompleteContext</b>, and <b>TransferLength</b> members to the specified values.

  Note that <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b> does <i>not</i> set the structure's <b>EvtUsbTargetPipeReadersFailed</b> member.

 After calling <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b>, the driver can optionally add a <b>EvtUsbTargetPipeReadersFailed</b> pointer to the <a href="..\wdfusb\ns-wdfusb-_wdf_usb_continuous_reader_config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.

For a code example that uses <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b>, see <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a>.




## -see-also

<a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a>



<a href="..\wdfusb\ns-wdfusb-_wdf_usb_continuous_reader_config.md">WDF_USB_CONTINUOUS_READER_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_CONTINUOUS_READER_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

