---
UID: NC:sercx.EVT_SERCX_APPLY_CONFIG
title: EVT_SERCX_APPLY_CONFIG
author: windows-driver-content
description: The EvtSerCxApplyConfig event callback function instructs the serial controller driver to apply a list of configuration settings to the serial controller hardware.
old-location: serports\evtsercxapplyconfig.htm
old-project: serports
ms.assetid: DC0AB4E3-AA73-4DD5-B91D-95F9D3792321
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercxapplyconfig, EvtSerCxApplyConfig callback function [Serial Ports], EvtSerCxApplyConfig, EVT_SERCX_APPLY_CONFIG, EVT_SERCX_APPLY_CONFIG, 1/EvtSerCxApplyConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	1.0\Sercx.h
apiname:
-	EvtSerCxApplyConfig
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---

# EVT_SERCX_APPLY_CONFIG callback


## -description


The <i>EvtSerCxApplyConfig</i> event callback function instructs the serial controller driver to apply a list of configuration settings to the serial controller hardware.


## -prototype


````
EVT_SERCX_APPLY_CONFIG EvtSerCxApplyConfig;

NTSTATUS EvtSerCxApplyConfig(
  _In_ WDFDEVICE Device,
  _In_ PVOID     ConnectionParameters
)
{ ... }
````


## -parameters




#### - Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


#### - ConnectionParameters [in]

A pointer to the connection parameters structure.  This function must cast this parameter to the appropriate pointer type, parse the data structure to obtain the configuration settings, and apply these settings to the serial controller hardware. The connection parameters structure is defined by the hardware platform vendor and is opaque to both the serial framework extension (SerCx) and the operating system.


## -returns


The <i>EvtSerCxApplyConfig</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.



## -remarks


SerCx calls this function during initialization of the serial controller to ensure that the hardware is in a valid initial state. Additionally, this function is called whenever a client sends an <a href="..\ntddser\ni-ntddser-ioctl_serial_apply_default_configuration.md">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a> I/O control request to the controller.

SerCx obtains these configuration parameters from the ACPI resource descriptor for the serial controller device. The data format that the ACPI firmware uses to store these configuration settings should be the same data format that is expected by the serial controller driver.

When a client sends an <b>IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</b> request to a serial port that is managed by SerCx, SerCx determines whether the serial controller driver for the serial port supports the <i>EvtSerCxApplyConfig</i> callback, and whether the ACPI resource descriptor for the serial port provides default connection settings. If not, SerCx completes the request with error status code STATUS_NOT_SUPPORTED. Otherwise, SerCx passes the connection parameters to the driver's <i>EvtSerCxApplyConfig</i> callback function. After this callback returns, SerCx completes the request and uses the return value from the callback as the status code for the request.

If a serial controller driver needs to obtain the default connection parameters at a time other than during an <i>EvtSerCxApplyConfig</i> callback, the driver can call the <a href="..\sercx\nf-sercx-sercxgetconnectionparameters.md">SerCxGetConnectionParameters</a> method.

To register an <i>EvtSerCxApplyConfig</i> callback function, the driver must call the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method.



## -see-also

<a href="..\sercx\nf-sercx-sercxgetconnectionparameters.md">SerCxGetConnectionParameters</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_apply_default_configuration.md">IOCTL_SERIAL_APPLY_DEFAULT_CONFIGURATION</a>

<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_APPLY_CONFIG callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

