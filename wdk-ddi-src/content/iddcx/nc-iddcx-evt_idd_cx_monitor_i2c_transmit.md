---
UID: NC:iddcx.EVT_IDD_CX_MONITOR_I2C_TRANSMIT
title: EVT_IDD_CX_MONITOR_I2C_TRANSMIT (iddcx.h)
description: EVT_IDD_CX_MONITOR_I2C_TRANSMIT is called by the OS to return data received to an I2C device in a monitor.
old-location: display\evt_idd_cx_monitor_i2c_transmit.htm
tech.root: display
ms.assetid: d36d45f5-fae1-430a-a01e-adb70e09573c
ms.date: 05/10/2018
ms.keywords: EVT_IDD_CX_MONITOR_I2C_TRANSMIT, EVT_IDD_CX_MONITOR_I2C_TRANSMIT callback, EvtIddCxMonitorI2cTransmit, EvtIddCxMonitorI2cTransmit callback function [Display Devices], PFN_IDD_CX_MONITOR_I2C_TRANSMIT, PFN_IDD_CX_MONITOR_I2C_TRANSMIT callback function pointer [Display Devices], display.evt_idd_cx_monitor_i2c_transmit, iddcx/EvtIddCxMonitorI2cTransmit
ms.topic: callback
f1_keywords:
 - "iddcx/PFN_IDD_CX_MONITOR_I2C_TRANSMIT"
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: _requires_same_
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- iddcx.h
api_name:
- PFN_IDD_CX_MONITOR_I2C_TRANSMIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_IDD_CX_MONITOR_I2C_TRANSMIT callback function


## -description


<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is called by the OS to return data received to an I2C device in a monitor.


## -parameters




### -param MonitorObject [in]

A handle used by the OS to identify the monitor to return I2C data to.


### -param pInArgs [in]

Input arguments used by <b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b>.


## -returns




(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code. 
                    




## -remarks



<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is responsible for signaling the I2C start condition, sending the I2C address, sending the data in the buffer, checking for acknowledgments from the receiver, and signaling the stop condition. For details about the I2C bus, see the I2C Bus Specification, published by Philips Semiconductors. The specification defines a protocol for initiating I2C communication, reading and writing bytes over the I2C data line, and terminating I2C
communication.


<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is required to transmit data to an I2C device that has address 0x6E but is permitted to refuse to transmit data to any I2C device that has a different address.


<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> is permitted to block if another part of the display driver or graphics hardware is using the specified monitor's I2C bus. It is also permitted to block if the display driver is using the I2C bus to send or receive High-bandwidth Digital Content Protection (HDCP) data.
<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> has a 5 second timeout and must complete in that time limit.

If the display adapter supports HDCP, <b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> must refuse to send data to an I2C device if the device has an I2C address that is used by HDCP.
<b>EVT_IDD_CX_MONITOR_I2C_TRANSMIT</b> must never transmit data to an I2C device on the display adapter. That is, this function can transmit data to an I2C device in a monitor that is connected to the display adapter, but not to an I2C device that is on the display adapter itself.



