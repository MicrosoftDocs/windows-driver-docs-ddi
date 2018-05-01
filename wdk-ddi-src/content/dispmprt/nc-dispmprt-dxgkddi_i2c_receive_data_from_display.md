---
UID: NC:dispmprt.DXGKDDI_I2C_RECEIVE_DATA_FROM_DISPLAY
title: DXGKDDI_I2C_RECEIVE_DATA_FROM_DISPLAY
author: windows-driver-content
description: The DxgkDdiI2CReceiveDataFromDisplay returns data received from an I2C device in a monitor.
old-location: display\dxgkddii2creceivedatafromdisplay.htm
old-project: display
ms.assetid: 7b412180-e453-4ae4-95a5-e5393e1d9197
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKDDI_I2C_RECEIVE_DATA_FROM_DISPLAY, DXGKDDI_I2C_RECEIVE_DATA_FROM_DISPLAY callback, DmFunctions_5fcf0936-1f93-4445-9a80-545ad88b472b.xml, DxgkDdiI2CReceiveDataFromDisplay, DxgkDdiI2CReceiveDataFromDisplay callback function [Display Devices], display.dxgkddii2creceivedatafromdisplay, dispmprt/DxgkDdiI2CReceiveDataFromDisplay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkDdiI2CReceiveDataFromDisplay
product: Windows
targetos: Windows
req.typenames: 
---

# DXGKDDI_I2C_RECEIVE_DATA_FROM_DISPLAY callback function


## -description


The <i>DxgkDdiI2CReceiveDataFromDisplay</i> returns data received from an I2C device in a monitor.


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param VidPnTargetId [in]

An integer that identifies one of the video present targets on the display adapter.


### -param SevenBitI2CAddress [in]

The address of the I2C device from which data will be received.


### -param Flags [in]

A value that specifies whether the length of the data is supplied as part of the data transmitted by the I2C device. This parameter must be set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
I2C_NO_FLAGS

</td>
<td>
The data length is supplied by the <i>DataLength</i> parameter. The I2C device does not supply the data length as part of the data that it transmits.

</td>
</tr>
<tr>
<td>
I2C_DEVICE_TRANSMITS_DATA_LENGTH

</td>
<td>
The data length is supplied by the I2C device as part of the data that it transmits. The I2C device transmits at least two bytes. The seven least significant bits of the second byte transmitted contain the intermediate length. You can calculate the number of bytes that will be transmitted after the byte that contains the intermediate length by adding one to the intermediate length.

</td>
</tr>
</table>
 


### -param DataLength [in]

The length, in bytes, of the buffer pointed to by <i>Data</i>.


### -param Data [out]

A pointer to a buffer that receives the data. The buffer can be in paged memory.


## -returns



<i>DxgkDdiI2CReceiveDataFromDisplay</i>returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>. The following list gives some of the possible error codes that can be returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_MONITOR_NOT_CONNECTED</b></dt>
</dl>
</td>
<td width="60%">
There is no monitor connected to the video output identified by <i>VidPnTargetId</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_I2C_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The video output identified by <i>VidPnTargetId</i> does not have an I2C bus.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_I2C_DEVICE_DOES_NOT_EXIST</b></dt>
</dl>
</td>
<td width="60%">
No device acknowledged the I2C address supplied in <i>SevenBitI2CAddress</i>. This could mean that no device on the I2C bus has the specified address or that an error occurred when the address was transmitted.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_I2C_ERROR_RECEIVING_DATA</b></dt>
</dl>
</td>
<td width="60%">
The I2C address was successfully transmitted, but there was an error receiving data from the I2C device.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The value supplied in <i>DataLength</i> is less than the required data buffer size. This return value is meaningful only if the I2C_DEVICE_TRANSMITS_DATA_LENGTH flag is set.

</td>
</tr>
</table>
 




## -remarks



The video present target identified by <i>VidPnTargetId</i> is associated with one of the video outputs on the display adapter. The data is received from an I2C device in the monitor that is connected to that video output. 

<i>DxgkDdiI2CReceiveDataFromDisplay</i> function is responsible for signaling the I2C start condition, sending the I2C address, receiving the data from the I2C device, sending acknowledgments, and signaling the stop condition. For details about the I2C bus, see the <i>I2C Bus Specification</i>, published by Philips Semiconductors. The specification defines a protocol for initiating I2C communication, reading and writing bytes over the I2C data line, and terminating I2C communication. (This resource may not be available in some languages 

and countries.)

<i>DxgkDdiI2CReceiveDataFromDisplay</i>is required to receive data from an I2C device that has address 0x6F but is permitted to refuse to receive data from any I2C device that has a different address.

<i>DxgkDdiI2CReceiveDataFromDisplay</i> is permitted to block if another part of the display miniport driver or graphics hardware is using the specified monitor's I2C bus. It is also permitted to block if the display miniport driver is using the I2C bus to send or receive High-bandwidth Digital Content Protection (HDCP) data.

If the display adapter supports HDCP, <i>DxgkDdiI2CReceiveDataFromDisplay</i> must refuse to receive data from an I2C device if the device has an I2C address that is used by HDCP.

<i>DxgkDdiI2CReceiveDataFromDisplay</i> must never receive data from an I2C device on the display adapter. That is, this function can receive data from an I2C device in a monitor that is connected to the display adapter, but not from an I2C device that is on the display adapter itself.

<i>DxgkDdiI2CReceiveDataFromDisplay</i> should be made pageable.




## -see-also




<a href="https://msdn.microsoft.com/67a08982-5d2f-4cd8-be14-76977fde0aac">DxgkDdiI2CTransmitDataToDisplay</a>
 

 

