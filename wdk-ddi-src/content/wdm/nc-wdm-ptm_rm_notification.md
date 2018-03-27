---
UID: NC:wdm.PTM_RM_NOTIFICATION
title: PTM_RM_NOTIFICATION
author: windows-driver-content
description: A resource manager's ResourceManagerNotification callback routine receives and handles transaction notifications.
old-location: kernel\resourcemanagernotification.htm
old-project: kernel
ms.assetid: 86d8632a-be39-46ed-8ec6-f65edb4bb017
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "(*PTM_RM_NOTIFICATION), (*PTM_RM_NOTIFICATION) callback function [Kernel-Mode Driver Architecture], PTM_RM_NOTIFICATION, kernel.resourcemanagernotification, ktm_ref_f4bc7393-b895-4a03-8eb6-b0a71f26e1d5.xml, wdm/(*PTM_RM_NOTIFICATION)"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	(*PTM_RM_NOTIFICATION)
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PTM_RM_NOTIFICATION callback


## -description


A resource manager's <i>ResourceManagerNotification</i> callback routine receives and handles <a href="https://msdn.microsoft.com/library/windows/hardware/ff564815">transaction notifications</a>.


## -parameters




### -param EnlistmentObject [in]

A pointer to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>. The <i>ResourceManagerNotification</i> callback routine is receiving a notification for the enlistment that this object represents.


### -param RMContext [in]

The value that the resource manager previously specified for the <i>RMKey</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564676">TmEnableCallbacks</a> routine.


### -param TransactionContext [in]

The value that the resource manager previously specified for the <i>EnlistmentKey</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a> routine.


### -param TransactionNotification [in]

One of the TRANSACTION_NOTIFY_<i>XXX</i> values that are defined in Ktmtypes.h. This value specifies the type of transaction notification that KTM sent to the caller.


### -param TmVirtualClock [in, out]

A pointer to a location that contains the <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a> at the time that KTM prepared the notification for delivery to the resource manager. If the callback routine increases this value before it returns, KTM updates the virtual clock to the new value. (Typically, resource managers do not modify the virtual clock value.)


### -param ArgumentLength [in]

The length, in bytes, of the buffer that the <i>Argument</i> parameter points to. This parameter is zero if a buffer is not available.


### -param Argument [in]

A pointer to a buffer that contains notification-specific arguments. This parameter is <b>NULL</b> if the notification that the <i>TransactionNotification</i> parameter specifies does not require an argument buffer. 

For a list of notifications that include an additional argument buffer, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff564813">TRANSACTION_NOTIFICATION</a>.


## -returns



<i>ResourceManagerNotification</i> callback routine must return STATUS_SUCCESS or another status value for which NT_SUCCESS(<b>status</b>) equals <b>TRUE</b> if the operation is successful.

Typically, the resource manager returns STATUS_SUCCESS if it services the notification synchronously and STATUS_PENDING if it services the notification asynchronously, but it can return STATUS_PENDING in either case. However, the resource manager can return STATUS_PENDING only for notifications that it responds to by calling one of the <b>Tm<i>Xxx</i>Complete</b> or <b>Zw<i>Xxx</i>Complete</b> routines.

In other words, if the resource manager must respond to a notification by calling one of the <b>Tm<i>Xxx</i>Complete</b> or <b>Zw<i>Xxx</i>Complete</b> routines, it can return STATUS_PENDING for the notification and later call the appropriate <b>Tm<i>Xxx</i>Complete</b> or <b>Zw<i>Xxx</i>Complete</b> routine.

If an error occurs, the callback routine must return a status value for which NT_SUCCESS(status) equals <b>FALSE</b>.




## -remarks



To register a <i>ResourceManagerNotification</i> callback routine, your resource manager must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564676">TmEnableCallbacks</a>.

Note that <i>ResourceManagerNotification</i> callback routines receive a pointer, instead of a handle, to an enlistment object. You can pass the enlistment object pointer to the enlistment object's <a href="https://msdn.microsoft.com/8bc763e9-e67c-4810-9901-e5dc1a1cfd0c">TmXxx routines</a>.

For more information about <i>ResourceManagerNotification</i> callback routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

The <i>ResourceManagerNotification</i> callback routine is called at IRQL = PASSIVE_LEVEL, and it must return at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564813">TRANSACTION_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564676">TmEnableCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566467">ZwGetNotificationResourceManager</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ResourceManagerNotification callback function%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

