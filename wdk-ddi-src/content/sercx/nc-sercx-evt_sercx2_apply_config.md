---
UID: NC:sercx.EVT_SERCX2_APPLY_CONFIG
title: EVT_SERCX2_APPLY_CONFIG
author: windows-driver-content
description: The EvtSerCx2ApplyConfig event callback function is called by version 2 of the serial framework extension (SerCx2) to supply the serial controller driver with a list of device-specific configuration settings to apply to the serial controller hardware.
old-location: serports\evtsercx2applyconfig.htm
old-project: serports
ms.assetid: 8D9BC698-1E62-4DC2-B233-37022F330F98
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2applyconfig, EvtSerCx2ApplyConfig callback function [Serial Ports], EvtSerCx2ApplyConfig, EVT_SERCX2_APPLY_CONFIG, EVT_SERCX2_APPLY_CONFIG, 2/EvtSerCx2ApplyConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	2.0\Sercx.h
apiname:
-	EvtSerCx2ApplyConfig
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX2_APPLY_CONFIG callback


## -description


The <i>EvtSerCx2ApplyConfig</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to supply the serial controller driver with a list of device-specific configuration settings to apply to the serial controller hardware.


## -prototype


````
EVT_SERCX2_APPLY_CONFIG EvtSerCx2ApplyConfig;

NTSTATUS EvtSerCx2ApplyConfig(
  _In_ WDFDEVICE Device,
  _In_ PVOID     ConnectionParameters
)
{ ... }
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.


### -param ConnectionParameters [in]

A pointer to the connection parameters structure. This function must cast the pointer to the appropriate pointer type, parse the data structure to obtain the configuration settings, and apply these settings to the serial controller hardware. The connection parameters structure is defined by the hardware platform vendor and is opaque to both SerCx2 and the operating system. For more information, see Remarks.


## -returns


The <i>EvtSerCx2ApplyConfig</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.



## -remarks


Your serial controller driver must implement this function. The driver registers the function in the call to the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

SerCx2 calls the <i>EvtSerCx2ApplyConfig</i> function during initialization of the serial controller to ensure that the hardware is in a valid initial state. Additionally, this function is called whenever a client sends an <a href="..\ntddser\ni-ntddser-ioctl_serial_apply_default_configuration.md">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a> request to the serial controller.

SerCx2 obtains the configuration parameters from the vendor-defined data field in the ACPI resource descriptor for the serial controller device. The data format that the ACPI firmware uses to store these configuration settings should be the same data format that is expected by the serial controller driver. For more information, see the description of the <i>UART serial bus connection descriptor</i> in the <i>Advanced Configuration and Power Interface Specification, Revision 5.0</i>, at the <a href="http://www.acpi.info">ACPI</a> website.

When a client sends an <b>IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</b> request to a serial port that is managed by SerCx2, SerCx2 calls the <i>EvtSerCx2ApplyConfig</i> function to pass the configuration parameters to the serial controller driver. After this callback returns, SerCx2 completes the request and uses the return value from the callback as the status code for the request.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj938063">RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_apply_default_configuration.md">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/jj938062">PNP_SERIAL_BUS_DESCRIPTOR</a>

<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_APPLY_CONFIG callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

