---
UID: NS:61883._SET_FCP_NOTIFY
title: "_SET_FCP_NOTIFY"
author: windows-driver-content
description: This structure is used for FCP notification.
old-location: ieee\set_fcp_notify.htm
tech.root: IEEE
ms.assetid: 94A966C4-9FFA-4937-B7D8-D1A3608E4A7F
ms.date: 02/15/2018
ms.keywords: "*PSET_FCP_NOTIFY, 61883/PSET_FCP_NOTIFY, 61883/SET_FCP_NOTIFY, IEEE.set_fcp_notify, PSET_FCP_NOTIFY, PSET_FCP_NOTIFY structure pointer [Buses], SET_FCP_NOTIFY, SET_FCP_NOTIFY structure [Buses], _SET_FCP_NOTIFY"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	SET_FCP_NOTIFY
product:
- Windows
targetos: Windows
req.typenames: SET_FCP_NOTIFY, *PSET_FCP_NOTIFY
---

# _SET_FCP_NOTIFY structure


## -description


This structure is used for FCP notification. The SetFcpNotify request registers a client driver notification of FCP requests or responses, or cancels a prior registration. A driver must register for FCP notifications in order to retrieve requests or responses. The driver is responsible for canceling registration by sending an SetFcpNotify request with DEREGISTER_FCP_NOTIFY set in <b>Flags</b> before the system unloads the driver. 


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
 

 

