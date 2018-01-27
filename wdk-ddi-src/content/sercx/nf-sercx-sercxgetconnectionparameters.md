---
UID: NF:sercx.SerCxGetConnectionParameters
title: SerCxGetConnectionParameters function
author: windows-driver-content
description: The SerCxGetConnectionParameters method retrieves the connection parameters for the associated peripheral device.
old-location: serports\sercxgetconnectionparameters.htm
old-project: serports
ms.assetid: 361BC3A7-AE86-4C92-B7E1-A30D467D4A65
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCxGetConnectionParameters, SerCxGetConnectionParameters method [Serial Ports], 1/SerCxGetConnectionParameters, serports.sercxgetconnectionparameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: <= DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	1.0\Sercx.h
apiname: 
-	SerCxGetConnectionParameters
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCxGetConnectionParameters function


## -description


The <b>SerCxGetConnectionParameters</b> method retrieves the connection parameters for the associated peripheral device.


## -syntax


````
VOID SerCxGetConnectionParameters(
  [in]  WDFDEVICE Device,
  [out] PVOID     *ConnectionParameters
);
````


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param ConnectionParameters [out]

A pointer to a location into which the method writes a pointer to the connection parameters. The caller must cast this pointer to the appropriate pointer type, parse the data structure for the connection parameters, read the configuration settings from this structure, and apply these settings to the serial controller hardware.


## -returns


None.



## -remarks


The serial framework extension (SerCx) obtains the connection parameters for the peripheral device from the ACPI resource descriptors in the platform firmware.

For more information about the data format of the connection parameters, see <a href="..\sercx\nc-sercx-evt_sercx_apply_config.md">EvtSerCxApplyConfig</a>.



## -see-also

<a href="..\sercx\nc-sercx-evt_sercx_apply_config.md">EvtSerCxApplyConfig</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxGetConnectionParameters method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

