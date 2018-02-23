---
UID: NF:mrx.RxRegisterMinirdr
title: RxRegisterMinirdr function
author: windows-driver-content
description: RxRegisterMinirdr is called by a network mini-redirector driver to register the driver with RDBSS, which adds the registration information to an internal registration table. RDBSS also builds a device object for the network mini-redirector.
old-location: ifsk\rxregisterminirdr.htm
old-project: ifsk
ms.assetid: f9c2fedd-b513-4ea9-b915-cdcc05b88d6f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxRegisterMinirdr function [Installable File System Drivers], rxref_72a33968-ea1e-4431-9843-5bf3aa11a12a.xml, mrx/RxRegisterMinirdr, RxRegisterMinirdr, ifsk.rxregisterminirdr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mrx.h
apiname:
-	RxRegisterMinirdr
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---

# RxRegisterMinirdr function


## -description


<b>RxRegisterMinirdr</b> is called by a network mini-redirector driver to register the driver with RDBSS, which adds the registration information to an internal registration table. RDBSS also builds a device object for the network mini-redirector. 


## -syntax


````
NTSTATUS RxRegisterMinirdr(
  _Out_   PRDBSS_DEVICE_OBJECT *DeviceObject,
  _Inout_ PDRIVER_OBJECT       DriverObject,
  _In_    PMINIRDR_DISPATCH    MrdrDispatch,
  _In_    ULONG                Controls,
  _In_    PUNICODE_STRING      DeviceName,
  _In_    ULONG                DeviceExtensionSize,
  _In_    DEVICE_TYPE          DeviceType,
  _In_    ULONG                DeviceCharacteristics
);
````


## -parameters




### -param DeviceObject [out]

A pointer to where the created device object will be stored.


### -param DriverObject [in, out]

A pointer to the driver object of the network mini-redirector driver. Each driver receives a pointer to its driver object in a parameter to its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine. This driver object will be used to create the device object for the network mini-redirector driver. 


### -param MrdrDispatch [in]

A pointer to the dispatch table for the network mini-redirector. This dispatch table includes configuration information for the network mini-redirector and a table of pointers to callback routines implemented by the network mini-redirector kernel driver. RDBSS makes calls to the network mini-redirector driver through this list of callback routines. 


### -param Controls [in]

The set of options that determine capabilities of the network mini-redirector driver and how RDBSS should handle initialization and name table caching for the network mini-redirector driver. These options can include any combination of the following bits:





#### RX_REGISTERMINI_FLAG_DONT_PROVIDE_UNCS

When this flag is set, it indicates that the network mini-redirector does not support UNC names.



#### RX_REGISTERMINI_FLAG_DONT_PROVIDE_MAILSLOTS

When this flag is set, it indicates that the network mini-redirector does not support mailslots.



#### RX_REGISTERMINI_FLAG_DONT_INIT_DRIVER_DISPATCH

When this flag is set, it indicates that the network mini-redirector does not want RDBSS to initialize the driver dispatch entry points of the mini-redirector driver to point to RDBSS internal routines. This option would only be used in unusual circumstances. Normally RDBSS would set the driver dispatch entry points and the fast I/O dispatch in the network mini-redirector driver object to point to routines internal to RDBSS.



#### RX_REGISTERMINI_FLAG_DONT_INIT_PREFIX_N_SCAVENGER

When this flag is set, it indicates that the network mini-redirector does not want RDBSS to initialize its internal network name table and scavenger data structures for scavenging this name table. This option would be set for a network mini-redirector that wants to handle caching for network share names itself and not use the RDBSS facilities for name caching and scavenging.


### -param DeviceName [in]

A pointer to a buffer that contains a zero-terminated Unicode string that names the device object. The string must be a full path name. This parameter is passed as <i>DeviceName</i> to the <b>IoCreateDevice</b> routine by RDBSS.


### -param DeviceExtensionSize [in]

The size specified by the mini-redirector driver for the number of bytes to be allocated for the device extension of the device object. The internal structure of the device extension is driver-defined. This parameter is added to the size of the device extension used by RDBSS and passed as the <i>DeviceExtensionSize</i> parameter to the <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> routine by RDBSS.


### -param DeviceType [in]

The device type used when the device object is created. This specifies one of the system-defined FILE_DEVICE_XXX constants that indicate the type of device or a vendor-defined value for a new type of device. This value would normally be FILE_DEVICE_NETWORK_FILE_SYSTEM for network mini-redirector drivers. This parameter is passed as <i>DeviceType</i> to the <b>IoCreateDevice</b> routine by RDBSS. 


### -param DeviceCharacteristics [in]

The device characteristics used when the device object is created. This specifies one or more system-defined constants, combined together, that provide additional information about the driver's device. This value must include FILE_REMOTE_DEVICE for network mini-redirector drivers, but this might be combined with other characteristics such as FILE_DEVICE_SECURE_OPEN. This parameter is passed as <i>DeviceCharacteristics</i> to the <b>IoCreateDevice</b> routine by RDBSS. 


## -returns



<b>RxRegisterMinirdr</b> returns STATUS_SUCCESS on success or one of the following error values on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There were insufficient resources to create the device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was passed to the routine. This error will be returned if the <i>DeviceObject</i> parameter is a <b>NULL</b> pointer. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_COLLISION</b></dt>
</dl>
</td>
<td width="60%">
A name collision occurred when trying to create this device object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
A device object with this name already exists.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The call to create the device object returned a <b>NULL</b> device object.

</td>
</tr>
</table>
 




## -remarks



A network mini-redirector registers with RDBSS whenever the driver is loaded by the kernel and unregisters with RDBSS when the driver is unloaded. A non-monolithic driver (the SMB network mini-redirector) communicates with the <i>Rdbss.sys</i>, another kernel driver. For a monolithic network mini-redirector driver that statically links with <i>Rdbsslib.lib</i>, this communication is merely a call to an <i>Rdbsslib.lib</i> library routine.

A network mini-redirector informs RDBSS that it has been loaded by calling <b>RxRegisterMinirdr</b>, the registration routine exported from RDBSS. When a network mini-redirector driver first starts (in its <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine), the driver calls the RDBSS <b>RxRegisterMinirdr</b> routine to register the network mini-redirector driver with RDBSS. Based on the parameters passed to <b>RxRegisterMinirdr</b>, RDBSS calls <a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a> to create the device object for the network mini-redirector driver. 

As part of this registration process, the network mini-redirector passes a parameter to <b>RxRegisterMinirdr</b> that is a pointer to a large structure, MINIRDR_DISPATCH, which contains configuration information for the network mini-redirector and a dispatch table of pointers to callback routines implemented by the network mini-redirector driver. This configuration data is used to configure internal RDBSS tables for use with this network mini-redirector. RDBSS uses the callback routines passed in this structure to communicate with the network mini-redirector. A network mini-redirector can chose to implement only some of these callback routines. Any callback routine that is not implemented should be set to a <b>NULL</b> pointer in the dispatch table passed to RDBSS. Only callback routines implemented by the network mini-redirector will be called by RDBSS. 

Note that the <b>RxRegisterMinirdr</b> routine sets all of the driver dispatch routines of the network mini-redirector driver to point to the top-level RDBSS dispatch routine, <b>RxFsdDispatch</b>. A network mini-redirector can override this behavior by saving a copy of its driver dispatch entry points, calling <b>RxRegisterMinirdr</b>, and rewriting the driver dispatch with its own entry points after the call to <b>RxRegisterMinirdr</b> returns. A network mini-redirector can also prevent its driver dispatch routines from being copied over by the <b>RxRegisterMinirdr</b> routine if the RX_REGISTERMINI_FLAG_DONT_INIT_DRIVER_DISPATCH bit is set in the <i>Controls</i> parameter.

If the <b>RxRegisterMinirdr</b> call is successful, a number of members in RDBSS_DEVICE_OBJECT pointed to by the <i>DeviceObject</i> parameter are initialized including the following: 

<ul>
<li>
The <b>Dispatch</b> member is set to the <i>MrdrDispatch</i> parameter.

</li>
<li>
The <b>RegistrationControls</b> member is set to the <i>Controls</i> parameter.

</li>
<li>
The <b>DeviceName</b> member is set to the <i>DeviceName</i> parameter.

</li>
<li>
The <b>RegisterUncProvider</b> member is set to <b>TRUE</b> if the RX_REGISTERMINI_FLAG_DONT_PROVIDE_UNCS bit in the <i>Controls</i> parameter was not set.

</li>
<li>
The <b>RegisterMailSlotProvider</b> member is set to <b>TRUE</b> if the RX_REGISTERMINI_FLAG_DONT_PROVIDE_MAILSLOTS bit in the <i>Controls</i> parameter was not set.

</li>
<li>
The <b>NetworkProviderPriority</b> member is set to the network provider priority that MUP will use.

</li>
</ul>
If the <b>RxRegisterMinirdr</b> call is successful and the RX_REGISTERMINI_FLAG_DONT_INIT_PREFIX_N_SCAVENGER bit in the <i>Controls</i> parameter is not set, a number of other members in RDBSS_DEVICE_OBJECT pointed to by the <i>DeviceObject</i> parameter are initialized, including the following: 

<ul>
<li>
The <b>pRxNetNameTable</b> member structure is initialized.

</li>
<li>
The <b>RxNetNameTableInDeviceObject.IsNetNameTable</b> member is set to <b>TRUE</b>.

</li>
<li>
The <b>pRdbssScavenger</b> member structure is initialized.

</li>
</ul>
If the <b>RxRegisterMinirdr</b> call is successful, RDBSS sets the internal state of the network mini-redirector in RDBSS to RDBSS_STARTABLE.

The network mini-redirector does not actually start operation until it receives a call to its <a href="..\mrx\nc-mrx-pmrx_calldown_ctx.md">MRxStart</a> routine, one of the callback routines passed in the MINIRDR_DISPATCH structure. The <b>MrxStart</b> callback routine must be implemented by the network mini-redirector driver if it wishes to receive callbacks for operations, unless the network mini-redirector preserves its own driver dispatch entry points. Otherwise, RDBSS will only allow the following I/O request packets through to the driver until <b>MrxStart</b> returns successfully:

<ul>
<li>
IRP requests for device create operations and device operations where the <i>FileObject-&gt;FileName.Length</i> parameter on the IRPSP is zero and the <i>FileObject-&gt;RelatedFileObject</i> parameter is <b>NULL</b>.

</li>
</ul>
For any other IRP request, the RDBSS dispatch routine, <a href="..\mrx\nf-mrx-rxfsddispatch.md">RxFsdDispatch</a>, will return a status of STATUS_REDIRECTOR_NOT_STARTED. 

The RDBSS dispatch routine will also fail any requests for the following I/O request packets:

<ul>
<li>
IRP_MJ_CREATE_MAILSLOT

</li>
<li>
IRP_MJ_CREATE_NAMED_PIPE

</li>
</ul>
The network mini-redirector <b>MrxStart</b> routine is called by RDBSS when the <b>RxStartMiniRdr</b> routine is called. The RDBSS <b>RxStartMinirdr</b> is usually called as a result of an FSCTL or IOCTL request from a user-mode application or service to start the network mini-redirector. The call to <b>RxStartMinirdr </b>cannot be made from the <b>DriverEntry</b> routine of the network mini-redirector after a successful call to <b>RxRegisterMinirdr </b>because some of the start processing requires that the driver initialization be completed. Once the <b>RxStartMinirdr</b> call is received, RDBSS completes the start process by calling the <b>MrxStart</b> routine of the network mini-redirector. If the call to <b>MrxStart</b> returns success, RDBSS sets the internal state of the mini-redirector in RDBSS to RDBSS_STARTED. 




## -see-also

<a href="..\mrx\nf-mrx-rxpunregisterminirdr.md">RxpUnregisterMinirdr</a>



<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



<a href="..\mrx\nf-mrx-rxfsddispatch.md">RxFsdDispatch</a>



<a href="..\rxstruc\nf-rxstruc-rxunregisterminirdr.md">RxUnregisterMinirdr</a>



<a href="..\mrx\nf-mrx-rxstartminirdr.md">RxStartMinirdr</a>



<a href="..\mrx\nf-mrx-rxsetdomainformailslotbroadcast.md">RxSetDomainForMailslotBroadcast</a>



<a href="..\mrx\nf-mrx-__rxfillandinstallfastiodispatch.md">__RxFillAndInstallFastIoDispatch</a>



<a href="..\wdm\nf-wdm-iocreatedevice.md">IoCreateDevice</a>



<a href="..\mrx\nf-mrx-rxstopminirdr.md">RxStopMinirdr</a>



<a href="..\mrx\nc-mrx-pmrx_calldown_ctx.md">MRxStart</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxRegisterMinirdr function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

