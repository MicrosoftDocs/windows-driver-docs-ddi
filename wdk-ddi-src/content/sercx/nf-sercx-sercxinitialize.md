---
UID: NF:sercx.SerCxInitialize
title: SerCxInitialize function
author: windows-driver-content
description: The SerCxInitialize method completes the initialization of the serial framework extension (SerCx) after this driver creates the associated device object.
old-location: serports\sercxinitialize.htm
old-project: serports
ms.assetid: 2837C3BE-71EB-4949-AB46-5333CF4575A8
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: 1/SerCxInitialize, SerCxInitialize, SerCxInitialize method [Serial Ports], serports.sercxinitialize
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	1.0\Sercx.h
api_name:
-	SerCxInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# SerCxInitialize function


## -description


The <b>SerCxInitialize</b> method completes the initialization of the serial framework extension (SerCx) after this driver creates the associated device object.


## -parameters




### -param FxDevice [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param Config [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439548">SERCX_CONFIG</a> structure that contains configuration information for SerCx. The caller previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439553">SERCX_CONFIG_INIT</a> function to initialize this structure.


## -returns



<b>SerCxInitialize</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The method was called at the wrong IRQL; or the WDFDEVICE handle is not valid; or either <i>FxDevice</i> or <i>Config</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Could not allocate system resources (typically memory).

</td>
</tr>
</table>
 




## -remarks



The serial controller driver calls this method after it creates the associated device object.

<b>SerCxInitialize</b> registers the controller driver’s I/O callback functions with SerCx. In addition, this method defines the transfer mode for the I/O queue.  During the call, this method creates all of the internal structures required by SerCx (including the I/O queue for the serial controller).  After this method returns, SerCx is ready to process I/O.  However, the controller driver might configure controller hardware settings before it returns from the <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback or before it adds the PDO to the child list.

If the parameters are invalid (as described in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439548">SERCX_CONFIG</a>), <a href="https://msdn.microsoft.com/library/windows/hardware/ff557262">Driver Verifier</a> will raise an error.

This routine must be called before committing the device (returning from <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> or adding the PDO to the child list).




## -see-also




<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439548">SERCX_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439553">SERCX_CONFIG_INIT</a>
 

 

