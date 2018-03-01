---
UID: NF:rxcontx.RxInitializeContext
title: RxInitializeContext function
author: windows-driver-content
description: RxInitializeContext initializes an existing RX_CONTEXT data structure.
old-location: ifsk\rxinitializecontext.htm
old-project: ifsk
ms.assetid: 71b595be-61ac-4a8f-af5e-d504e5091e0c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxInitializeContext, RxInitializeContext function [Installable File System Drivers], ifsk.rxinitializecontext, rxcontx/RxInitializeContext, rxref_4092dc37-eda5-4293-ab39-bec3ed2753f6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxcontx.h
req.include-header: Rxprocs.h  rxcontx.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxcontx.h
api_name:
-	RxInitializeContext
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxInitializeContext function


## -description


<b>RxInitializeContext</b> initializes an existing RX_CONTEXT data structure. 


## -syntax


````
VOID RxInitializeContext(
  _In_opt_ PIRP                 Irp,
  _In_     PRDBSS_DEVICE_OBJECT RxDeviceObject,
  _In_     ULONG                InitialContextFlags,
  _Inout_  PRX_CONTEXT          RxContext
);
````


## -parameters




### -param Irp [in, optional]

A pointer to the IRP to be encapsulated by this RX_CONTEXT structure.


### -param RxDeviceObject [in]

A pointer to the device object to which this RX_CONTEXT and IRP apply.


### -param InitialContextFlags [in]

The set of initial values for <i>Flags</i> member of the RX_CONTEXT data structure to be stored in the RX_CONTEXT structure. These initial values can be any combination of the following enumerations:





#### RX_CONTEXT_FLAG_WAIT

When this value is set, the IRP should be not be posted for later execution by the file system process, but should be waited on to complete.



#### RX_CONTEXT_FLAG_MUST_SUCCEED

When this value is set, the operation must succeed. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers. 



#### RX_CONTEXT_FLAG_MUST_SUCCEED_NONBLOCKING

When this value is set, the operation must succeed for non-blocking operations. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers. 


### -param RxContext [in, out]

Pointer to the RX_CONTEXT to be initialized.


## -returns



None 




## -remarks



<b>RxInitializeContext</b> is called internally by the <b>RxCreateRxContext</b> routine. So the <b>RxInitializeContext</b> routine would normally only be used by network min-redirector drivers that allocate RX_CONTEXT structures directly rather than calling the <b>RxCreateRxContext</b> routine to allocate and initialize an RX_CONTEXT structure. 

If the <i>Irp</i> parameter is configured for asynchronous operation, then the <b>Flags</b> member of the RX_CONTEXT structure pointed to by <i>RxContext</i> also has the following value set:



RX_CONTEXT_FLAG_ASYNC_OPERATION is also set for the following conditions:

<ul>
<li>
The <b>MajorFunction</b> member of the <i>Irp</i> is IRP_MJ_READ, IRP_MJ_WRITE, or IRP_MJ_DEVICE_CONTROL.

</li>
<li>
The <b>MajorFunction</b> member of the <i>Irp</i> is an IRP_MJ_DIRECTORY_CONTROL and the <b>MinorFunction</b> member of the <i>IRP</i> is an IRP_MN_NOTIFY_CHANGE_DIRECTORY.

</li>
<li>
The <b>MajorFunction</b> member of the <i>Irp</i> is an IRP_MJ_FILE_SYSTEM_CONTROL and <b>NetRoot</b> member of the associated FCB is not <b>NULL</b> and the <b>Type</b> member of the NET_ROOT is NET_ROOT_PIPE.

</li>
</ul>
If this is a recursive file system call (the TopLevelIrp member in the thread local storage is the current <i>Irp</i>) then the <b>Flags</b> member of <i>RxContext</i> also has the following value set:



If the <i>RxDeviceObject</i> parameter indicates that this is the top level RDBSS device object, then the <b>Flags</b> member of the RX_CONTEXT structure also has the following value set:



If the <i>Irp</i> FileObject Flags member has the FO_WRITE_THROUGH option set, then the <b>Flags</b> member of the RX_CONTEXT structure also has the following value set:



<b>RxInitializeContext</b> sets a number of other members in the RX_CONTEXT structure including the following:

<ul>
<li>
Sets the proper <b>NodeTypeCode</b>, <b>NodeByteSize</b>, <b>SerialNumber</b>, <b>RxDeviceObject</b>, and initializes the <b>ReferenceCount</b> to 1.

</li>
<li>
Initializes the SyncEvent

</li>
<li>
Initialize the associated ScavengerEntry

</li>
<li>
Initializes the list entry of BlockedOperations

</li>
<li>
Sets the RX_CONTEXT members based on the <i>Irp</i>. These include <b>CurrentIrp</b>, <b>OriginalThread</b>, <b>MajorFunction</b>, <b>MinorFunction</b>, <b>CurrentIrpSp</b>, <b>pFcb</b>, <b>NonPagedFcb</b>, <b>pFobx</b>, <b>pRelevantSrvOpen</b>, and <b>FobxSerialNumber</b> members.

</li>
</ul>



## -see-also

<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>



<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>



<a href="..\rxcontx\nf-rxcontx-__rxsynchronizeblockingoperations.md">__RxSynchronizeBlockingOperations</a>



<a href="..\rxprocs\nf-rxprocs-rxcompleterequest.md">RxCompleteRequest</a>



<a href="..\rxcontx\ns-rxcontx-_rx_context.md">RX_CONTEXT</a>



<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>



<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>



<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>



<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxInitializeContext function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

