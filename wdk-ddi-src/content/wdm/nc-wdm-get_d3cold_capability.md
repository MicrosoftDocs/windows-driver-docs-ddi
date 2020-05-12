---
UID: NC:wdm.GET_D3COLD_CAPABILITY
title: GET_D3COLD_CAPABILITY (wdm.h)
description: The GetBusDriverD3ColdSupport routine enables the driver for a device to query whether the enumerating bus driver supports the D3cold device power state.
old-location: kernel\getbusdriverd3coldsupport.htm
tech.root: kernel
ms.assetid: FE756171-327B-40E7-92A4-9159C509FD5E
ms.date: 04/30/2018
keywords: ["GET_D3COLD_CAPABILITY callback function"]
ms.keywords: GET_D3COLD_CAPABILITY, GetBusDriverD3ColdSupport, GetBusDriverD3ColdSupport routine [Kernel-Mode Driver Architecture], kernel.getbusdriverd3coldsupport, wdm/GetBusDriverD3ColdSupport
f1_keywords:
 - "wdm/GetBusDriverD3ColdSupport"
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- GetBusDriverD3ColdSupport
product:
- Windows
targetos: Windows
req.typenames: 
---

# GET_D3COLD_CAPABILITY callback function


## -description


The <i>GetBusDriverD3ColdSupport</i> routine enables the driver for a device to query whether the enumerating bus driver supports the D3cold device power state.


## -parameters




### -param Context [in, optional]

A pointer to interface-specific context information. The caller sets this parameter to the value of the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_d3cold_support_interface">D3COLD_SUPPORT_INTERFACE</a> structure for the interface.


### -param D3ColdSupported [out]

A pointer to a BOOLEAN variable to which the routine writes a value to indicate whether the bus driver supports the D3cold. If this value is <b>TRUE</b>, the bus driver supports D3cold. If <b>FALSE</b>, the bus driver does not support D3cold. If the call fails, the routine returns an error status code and does not write anything to this variable.


## -returns



The <i>GetBusDriverD3ColdSupport</i> routine returns STATUS_SUCCESS if it is successful. Otherwise, it returns an appropriate error status code.




## -remarks



The driver for the device calls the version of this routine that is implemented by the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/acpi-driver">Windows ACPI driver</a>, Acpi.sys. This routine checks the parent bus driver for the device to determine whether this bus driver supports the D3cold power state.

For example, starting with Windows 8, Microsoft supplies an inbox USB 3.0 eXtensible Host Controller Interface (xHCI) driver that supports D3cold. Some third-party hardware vendors supply Windows drivers for their xHCI controllers, but these drivers might not support D3cold. The driver for a USB 3.0 device can call the <i>GetBusDriverD3ColdSupport</i> routine to determine whether the parent xHCI controller driver supports D3cold.

A bus driver supports D3cold if all of the following are true:

<ul>
<li>The bus driver implements the GUID_D3COLD_SUPPORT_INTERFACE driver interface.</li>
<li>The bus driver implements the <i>GetBusDriverD3ColdSupport</i> routine in this interface.</li>
<li>The output value from the <i>GetBusDriverD3ColdSupport</i> routine indicates that the bus driver supports D3cold.</li>
</ul>
The driver for a device can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_idle_wake_info">GetIdleWakeInfo</a> routine to determine whether the underlying bus drivers and ACPI system firmware support D3cold for the device. If this call fails and returns an error status code, the device driver can call the <i>GetBusDriverD3ColdSupport</i> routine to determine whether the failure is caused by lack of D3cold support by the parent bus driver.

A device on a bus can make a transition to the D3cold substate only if the bus driver supports this transition. If the bus driver does not support D3cold, the device never enters D3cold, even if the function driver for the device calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-set_d3cold_support">SetD3ColdSupport</a> routine to enable the transition to D3cold. In this case, <i>SetD3ColdSupport</i> calls have no effect, but are harmless.

For this reason, most device drivers never need to call the <i>GetBusDriverD3ColdSupport</i> routine.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_d3cold_support_interface">D3COLD_SUPPORT_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967714">GUID_D3COLD_SUPPORT_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_idle_wake_info">GetIdleWakeInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-set_d3cold_support">SetD3ColdSupport</a>
 

 

