---
UID: NF:wdm.PoFxPowerControl
title: PoFxPowerControl function
description: The PoFxPowerControl routine sends a power control request to the power management framework (PoFx).
old-location: kernel\pofxpowercontrol.htm
tech.root: kernel
ms.assetid: B821AF54-AF2C-4E19-BC70-2E0A8F172D93
ms.date: 04/30/2018
ms.keywords: PoFxPowerControl, PoFxPowerControl routine [Kernel-Mode Driver Architecture], kernel.pofxpowercontrol, wdm/PoFxPowerControl
ms.topic: function
req.header: wdm.h
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	PoFxPowerControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxPowerControl function


## -description


The <b>PoFxPowerControl</b> routine sends a power control request to the power management framework (PoFx).


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a> routine.


### -param PowerControlCode [in]

A pointer to the power control code. This code is a GUID value that specifies the requested operation.


### -param InBuffer [in, optional]

A pointer to a caller-allocated buffer that contains the input data for the operation. The format for the data in this buffer depends on the power control code specified by the <i>PowerControlCode</i> parameter. The <i>InBuffer</i> parameter is optional and can be specified as NULL if the specified operation requires no input data.


### -param InBufferSize [in]

The size, in bytes, of the input buffer that is pointed to by the <i>InBuffer</i> parameter. If <i>InBuffer</i> is NULL, set <i>InBufferSize</i> to zero.


### -param OutBuffer [out, optional]

A pointer to a caller-allocated buffer that is to contain the output data from the operation. The format for the data in this buffer depends on the power control code specified by the <i>PowerControlCode</i> parameter. The <i>OutBuffer</i> parameter is optional and can be specified as NULL if the specified operation produces no output data.


### -param OutBufferSize [in]

The size, in bytes, of the output buffer that is pointed to by the <i>OutBuffer</i> parameter. If <i>OutBuffer</i> is NULL, set <i>OutBufferSize</i> to zero.


### -param BytesReturned [out, optional]

A pointer to a location into which the routine writes the number of bytes of data that were written to the buffer that is pointed to by <i>OutBuffer</i>. The number of bytes written will be less than or equal to <i>OutBufferSize</i>. This parameter is optional and can be specified as <b>NULL</b> if the caller does not need to know how many bytes were written to the output buffer.


## -returns



<b>PoFxPowerControl</b> returns <b>STATUS_SUCCESS</b> if the requested operation succeeds. Possible error return values include the following status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The requested power control operation is not implemented.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The power engine plug-in (PEP) does not acknowledge support for this device.

</td>
</tr>
</table>
 




## -remarks



A device driver calls this routine to send a power control request directly to PoFx. A power control request is similar to an I/O control request (IOCTL). Unlike an IOCTL, however, a power control request is sent directly to PoFx and is not observed by other device drivers in the device stack. During a <b>PoFxPowerControl</b> call, PoFx synchronously performs the requested operation.

Similarly, PoFx can send a power control request directly to the device driver. The driver handles this request in its <a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a> routine.

PoFx delegates the handling of all power control requests to the power engine plug-in (PEP). The PEP is an optional software component that performs power management tasks that are specific to a particular product line of processor or System on a Chip (SoC) modules. If the hardware vendor for the processor or SoC supplies a PEP for a hardware platform, this PEP might handle custom power control requests from a device driver, or might send custom power control requests to the driver's <i>PowerControlCallback</i> routine. The vendor can specify a set of <i>PowerControlCode</i> GUIDs and define the operations that are designated by these GUIDs. As an option, a device driver can contain platform-specific code to handle or to send requests for these operations.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439521">PoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a>
 

 

