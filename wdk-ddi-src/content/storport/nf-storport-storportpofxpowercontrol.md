---
UID: NF:storport.StorPortPoFxPowerControl
title: StorPortPoFxPowerControl function
author: windows-driver-content
description: The StorPortPoFxPowerControl routine sends a power control request to the power management framework (PoFx) to forward to the power engine plug-in (PEP).
old-location: storage\storportpofxpowercontrol.htm
old-project: storage
ms.assetid: 1EBEBD5D-E0E5-48A3-8CDA-C336575E53C6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.storportpofxpowercontrol, storport/StorPortPoFxPowerControl, StorPortPoFxPowerControl routine [Storage Devices], StorPortPoFxPowerControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows 8.
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
req.lib: Storport.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	storport.lib
-	storport.dll
apiname:
-	StorPortPoFxPowerControl
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortPoFxPowerControl function


## -description


The <b>StorPortPoFxPowerControl</b> routine sends a power control request to the power management framework (PoFx) to forward to the power engine plug-in (PEP).


## -syntax


````
ULONG StorPortPoFxPowerControl(
  _In_      PVOID   HwDeviceExtension,
  _In_      LPCGUID PowerControlCode,
  _In_opt_  PVOID   InBuffer,
  _In_      SIZE_T  InBufferSize,
  _Out_opt_ PVOID   OutBuffer,
  _In_      SIZE_T  OutBufferSize,
  _Out_opt_ PSIZE_T BytesReturned
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA). This is the device extension used to register the device in a prior call to <a href="..\storport\nf-storport-storportinitializepofxpower.md">StorPortInitializePoFxPower</a>.


### -param Address

TBD


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



The <b>StorPortPoFxPowerControl</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The power control operation specified in <i>PowerControlCode</i> was successfully executed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Either <i>HwDeviceExtension</i> or <i>Device</i> is NULL.

-or-

<i>Address</i> points to an invalid unit address structure.

-or-

The storage device specified by <i>Address</i> is not found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The storage device is  not registered with the PoFx.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
The current IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The power control operation was unsuccessful.

</td>
</tr>
</table>
 




## -remarks



A minport driver calls this routine to send a power control request directly to the PEP. A power control request is similar to an I/O control request (IOCTL). Unlike an IOCTL, however, a power control request is sent directly to PEP and is not observed by other device drivers in the device stack. During a <b>StorPortPoFxPowerControl</b> call, the PEP synchronously performs the requested operation.

Similarly, The PEP can send a power control request directly to the miniport. The miniport driver handles this request in its <a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a> and <a href="..\storport\nc-storport-hw_unit_control.md">HwStorUnitControl</a> routines. The <i>ControlType</i> parameter receives the <b>ScsiAdapterPoFxPowerControl</b> type in the <b>HwStorAdapterControl</b> routine and the <b>ScsiUnitPoFxPowerControl</b> in the <b>HwStorUnitControl</b> routine.




## -see-also

<a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a>



<a href="..\storport\nc-storport-hw_unit_control.md">HwStorUnitControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortPoFxPowerControl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

