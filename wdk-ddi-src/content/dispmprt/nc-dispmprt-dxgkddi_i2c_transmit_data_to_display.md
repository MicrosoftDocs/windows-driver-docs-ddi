---
UID: NC:dispmprt.DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY
title: DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY
author: windows-driver-content
description: The DxgkDdiI2CTransmitDataToDisplay function transmits data to an I2C device in a monitor.
old-location: display\dxgkddii2ctransmitdatatodisplay.htm
old-project: display
ms.assetid: 67a08982-5d2f-4cd8-be14-76977fde0aac
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgkddii2ctransmitdatatodisplay, DxgkDdiI2CTransmitDataToDisplay callback function [Display Devices], DxgkDdiI2CTransmitDataToDisplay, DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY, DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY, dispmprt/DxgkDdiI2CTransmitDataToDisplay, DmFunctions_6152910a-6f9c-4686-b025-2508bbfdf257.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dispmprt.h
apiname:
-	DxgkDdiI2CTransmitDataToDisplay
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY callback


## -description


The <i>DxgkDdiI2CTransmitDataToDisplay</i> function transmits data to an I2C device in a monitor.


## -prototype


````
DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY DxgkDdiI2CTransmitDataToDisplay;

NTSTATUS DxgkDdiI2CTransmitDataToDisplay(
  _In_       PVOID                          MiniportDeviceContext,
  _In_       D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId,
  _In_       ULONG                          SevenBitI2CAddress,
  _In_       ULONG                          DataLength,
  _In_ const PVOID                          Data
)
{ ... }
````


## -parameters




### -param MiniportDeviceContext [in]

A handle to a context block that is associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem.


### -param VidPnTargetId [in]

An integer that identifies one of the video present targets on the display adapter.


### -param SevenBitI2CAddress [in]

The address of the I2C device to which data will be transmitted.


### -param DataLength [in]

The length, in bytes, of the data to be transmitted. This parameter must be between 1 and 64, inclusive.


### -param PVOID








#### - Data [in]

A pointer to a buffer that holds the data to be transmitted.


## -returns



<i>DxgkDdiI2CTransmitDataToDisplay</i> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h. The following list gives some of the possible error codes that can be returned.

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
<dt><b>STATUS_GRAPHICS_I2C_ERROR_TRANSMITTING_DATA</b></dt>
</dl>
</td>
<td width="60%">
The I2C address was successfully transmitted, but there was an error transmitting data to the I2C device.

</td>
</tr>
</table>
 




## -remarks



The video present target identified by <i>VidPnTargetId</i> is associated with one of the video outputs on the display adapter. The data is transmitted to an I2C device in the monitor that is connected to that video output. 

<i>DxgkDdiI2CTransmitDataToDisplay</i> is responsible for signaling the I2C start condition, sending the I2C address, sending the data in the buffer, checking for acknowledgments from the receiver, and signaling the stop condition. For details about the I2C bus, see the <i>I2C Bus Specification</i>, published by Philips Semiconductors. The specification defines a protocol for initiating I2C communication, reading and writing bytes over the I2C data line, and terminating I2C communication. 

<i>DxgkDdiI2CTransmitDataToDisplay</i> is required to transmit data to an I2C device that has address 0x6E but is permitted to refuse to transmit data to any I2C device that has a different address.

<i>DxgkDdiI2CTransmitDataToDisplay</i> is permitted to block if another part of the display miniport driver or graphics hardware is using the specified monitor's I2C bus. It is also permitted to block if the display miniport driver is using the I2C bus to send or receive High-bandwidth Digital Content Protection (HDCP) data.

If the display adapter supports HDCP, the <i>DxgkDdiI2CTransmitDataToDisplay</i> function must refuse to send data to an I2C device if the device has an I2C address that is used by HDCP.

<i>DxgkDdiI2CTransmitDataToDisplay</i> must never transmit data to an I2C device on the display adapter. That is, this function can transmit data to an I2C device in a monitor that is connected to the display adapter, but not to an I2C device that is on the display adapter itself.

<i>DxgkDdiI2CTransmitDataToDisplay</i> should be made pageable.




## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_i2c_receive_data_from_display.md">DxgkDdiI2CReceiveDataFromDisplay</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_I2C_TRANSMIT_DATA_TO_DISPLAY callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

