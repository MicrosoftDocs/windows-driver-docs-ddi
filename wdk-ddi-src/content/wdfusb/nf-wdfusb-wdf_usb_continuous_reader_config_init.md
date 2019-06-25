---
UID: NF:wdfusb.WDF_USB_CONTINUOUS_READER_CONFIG_INIT
title: WDF_USB_CONTINUOUS_READER_CONFIG_INIT function (wdfusb.h)
description: The WDF_USB_CONTINUOUS_READER_CONFIG_INIT function initializes a WDF_USB_CONTINUOUS_READER_CONFIG structure.
old-location: wdf\wdf_usb_continuous_reader_config_init.htm
tech.root: wdf
ms.assetid: d9bf6c47-b7ce-413d-8871-4d9d68e27715
ms.date: 02/26/2018
ms.keywords: DFUsbRef_a179cacd-e450-4a53-93e7-4eb3a59fc605.xml, WDF_USB_CONTINUOUS_READER_CONFIG_INIT, WDF_USB_CONTINUOUS_READER_CONFIG_INIT function, kmdf.wdf_usb_continuous_reader_config_init, wdf.wdf_usb_continuous_reader_config_init, wdfusb/WDF_USB_CONTINUOUS_READER_CONFIG_INIT
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfusb.h
api_name:
- WDF_USB_CONTINUOUS_READER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_USB_CONTINUOUS_READER_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure. 


## -parameters




### -param Config [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.


### -param EvtUsbTargetPipeReadComplete [in]

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a> callback function.


### -param EvtUsbTargetPipeReadCompleteContext [in]

An untyped pointer to driver-defined context information that the framework passes to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a> callback function.


### -param TransferLength [in]

The maximum length, in bytes, of data that can be received from the device.


## -returns



None




## -remarks



The <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>EvtUsbTargetPipeReadComplete</b>, <b>EvtUsbTargetPipeReadCompleteContext</b>, and <b>TransferLength</b> members to the specified values.

  Note that <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b> does <i>not</i> set the structure's <b>EvtUsbTargetPipeReadersFailed</b> member.

 After calling <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b>, the driver can optionally add a <b>EvtUsbTargetPipeReadersFailed</b> pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a> structure.

For a code example that uses <b>WDF_USB_CONTINUOUS_READER_CONFIG_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader">WdfUsbTargetPipeConfigContinuousReader</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nc-wdfusb-evt_wdf_usb_reader_completion_routine">EvtUsbTargetPipeReadComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/ns-wdfusb-_wdf_usb_continuous_reader_config">WDF_USB_CONTINUOUS_READER_CONFIG</a>
 

 

