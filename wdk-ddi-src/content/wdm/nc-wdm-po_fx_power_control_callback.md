---
UID: NC:wdm.PO_FX_POWER_CONTROL_CALLBACK
title: PO_FX_POWER_CONTROL_CALLBACK
author: windows-driver-content
description: The PowerControlCallback callback routine performs a power control operation that is requested by the power management framework (PoFx).
old-location: kernel\powercontrolcallback.htm
old-project: kernel
ms.assetid: 110DAD1A-606B-4973-8724-03B531B2AEA9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.powercontrolcallback, PowerControlCallback routine [Kernel-Mode Driver Architecture], PowerControlCallback, PO_FX_POWER_CONTROL_CALLBACK, PO_FX_POWER_CONTROL_CALLBACK, wdm/PowerControlCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	PowerControlCallback
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# PO_FX_POWER_CONTROL_CALLBACK callback


## -description


The <i>PowerControlCallback</i> callback routine performs a power control operation that is requested by the power management framework (PoFx).


## -prototype


````
PO_FX_POWER_CONTROL_CALLBACK PowerControlCallback;

NTSTATUS PowerControlCallback(
  _In_      PVOID   Context,
  _In_      LPCGUID PowerControlCode,
  _In_opt_  PVOID   InBuffer,
  _In_      SIZE_T  InBufferSize,
  _Out_opt_ PVOID   OutBuffer,
  _In_      SIZE_T  OutBufferSize,
  _Out_opt_ PSIZE_T BytesReturned
)
{ ... }
````


## -parameters




### -param DeviceContext


### -param PowerControlCode [in]

A pointer to the power control code. This code is a GUID value that specifies the requested operation.


### -param InBuffer [in, optional]

A pointer to the buffer that contains the input data for the operation. The format for the data in this buffer depends on the power control code specified by the <i>PowerControlCode</i> parameter. The <i>InBuffer</i> parameter is optional and can be specified as NULL if the specified operation requires no input data.


### -param InBufferSize [in]

The size, in bytes, of the input buffer that is pointed to by the <i>InBuffer</i> parameter. If <i>InBuffer</i> is NULL, this parameter is zero.


### -param OutBuffer [out, optional]

A pointer to the buffer to which the callback routine writes the output data from the operation. The format for the data in this buffer depends on the power control code specified by the <i>PowerControlCode</i> parameter.  The <i>OutBuffer</i> parameter is optional and can be specified as NULL if the specified operation produces no output data.


### -param OutBufferSize [in]

The size, in bytes, of the output buffer that is pointed to by the <i>OutBuffer</i> parameter. If <i>OutBuffer</i> is NULL, this parameter is zero.


### -param BytesReturned [out, optional]

A pointer to a location into which the routine writes the number of bytes of data that were written to the buffer that is pointed to by <i>OutBuffer</i>. The number of bytes written must be less than or equal to <i>OutBufferSize</i>. This parameter is optional and can be specified as NULL if the caller does not need to know how many bytes were written to the output buffer.


#### - Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the driver used to register the device with PoFx. This context is opaque to PoFx.


## -returns



The <i>PowerControlCallback</i> routine returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



PoFx calls this routine to send a power control request directly to the device driver. A power control request is similar to an I/O control request (IOCTL). Unlike an IOCTL, however, a power control request is sent directly to the driver and is not observed by other device drivers in the device stack. During a <i>PowerControlCallback</i> call, the driver synchronously performs the requested operation.

This routine is optional. A device driver that does not support power control operations is not required to implement a <i>PowerControlCallback</i> routine.

The device driver can call the <a href="..\wdm\nf-wdm-pofxpowercontrol.md">PoFxPowerControl</a> routine to send a power control request to PoFx.

For more information about power control requests, see <a href="..\wdm\nf-wdm-pofxpowercontrol.md">PoFxPowerControl</a>.


#### Examples

To define a <i>PowerControlCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>PowerControlCallback</i> callback routine that is named <code>MyPowerControlCallback</code>, use the PO_FX_POWER_CONTROL_CALLBACK type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PO_FX_POWER_CONTROL_CALLBACK MyPowerControlCallback;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
  MyPowerControlCallback(
    PVOID Context,
    LPCGUID PowerControlCode,
    PVOID InBuffer,
    SIZE_T InBufferSize,
    PVOID OutBuffer,
    SIZE_T OutBufferSize,
    PSIZE_T BytesReturned
    )
  {
      // Function body
  }</pre>
</td>
</tr>
</table></span></div>
The PO_FX_POWER_CONTROL_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the PO_FX_POWER_CONTROL_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a>



<a href="..\wdm\nf-wdm-pofxpowercontrol.md">PoFxPowerControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PowerControlCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

