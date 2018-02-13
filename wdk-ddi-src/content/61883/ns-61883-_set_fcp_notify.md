---
UID: NS:61883._SET_FCP_NOTIFY
title: "_SET_FCP_NOTIFY"
author: windows-driver-content
description: This structure is used for FCP notification.
old-location: ieee\set_fcp_notify.htm
old-project: IEEE
ms.assetid: 94A966C4-9FFA-4937-B7D8-D1A3608E4A7F
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SET_FCP_NOTIFY structure [Buses], PSET_FCP_NOTIFY, _SET_FCP_NOTIFY, PSET_FCP_NOTIFY structure pointer [Buses], SET_FCP_NOTIFY, 61883/SET_FCP_NOTIFY, *PSET_FCP_NOTIFY, IEEE.set_fcp_notify, 61883/PSET_FCP_NOTIFY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	61883.h
apiname:
-	SET_FCP_NOTIFY
product: Windows
targetos: Windows
req.typenames: SET_FCP_NOTIFY, *PSET_FCP_NOTIFY
---

# _SET_FCP_NOTIFY structure


## -description


This structure is used for FCP notification. The SetFcpNotify request registers a client driver notification of FCP requests or responses, or cancels a prior registration. A driver must register for FCP notifications in order to retrieve requests or responses. The driver is responsible for canceling registration by sending an SetFcpNotify request with DEREGISTER_FCP_NOTIFY set in <b>Flags</b> before the system unloads the driver. 


## -syntax


````
typedef struct _SET_FCP_NOTIFY {
  ULONG        Flags;
  NODE_ADDRESS NodeAddress;
} SET_FCP_NOTIFY, *PSET_FCP_NOTIFY;
````


## -struct-fields




### -field Flags

On input, specifies the notification requested by the driver. The driver can register by setting <b>Flags</b> with either or both of the following: 

REGISTER_FCP_RESPONSE_NOTIFY

REGISTER_FCP_REQUEST_NOTIFY 

The driver can cancel notification by setting <b>Flags</b> with DEREGISTER_FCP_NOTIFY, which clears REGISTER_FCP_RESPONSE_NOTIFY and REGISTER_FCP_REQUEST_NOTIFY.


### -field NodeAddress

Reserved for use by the operating system.


## -remarks



If successful, the IEC-61883 protocol driver sets <b>Irp-&gt;IoStatus.Status </b>to STATUS_SUCCESS. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SET_FCP_NOTIFY structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

