---
UID: NS:iscsiop._LogoutFromTarget_OUT
title: _LogoutFromTarget_OUT (iscsiop.h)
description: The LogoutFromTarget_OUT structure holds the output data for the LogoutFromTarget method.
old-location: storage\logoutfromtarget_out.htm
tech.root: storage
ms.assetid: 15231188-5c6d-4e36-afe9-74b92f445fa3
ms.date: 03/29/2018
keywords: ["LogoutFromTarget_OUT structure"]
ms.keywords: "*PLogoutFromTarget_OUT, LogoutFromTarget_OUT, LogoutFromTarget_OUT structure [Storage Devices], PLogoutFromTarget_OUT, PLogoutFromTarget_OUT structure pointer [Storage Devices], _LogoutFromTarget_OUT, iscsiop/LogoutFromTarget_OUT, iscsiop/PLogoutFromTarget_OUT, storage.logoutfromtarget_out, structs-iSCSI_3ef612e0-305e-4015-8b77-5c2577e2b6aa.xml"
f1_keywords:
 - "iscsiop/LogoutFromTarget_OUT"
 - "LogoutFromTarget_OUT"
req.header: iscsiop.h
req.include-header: Iscsiop.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iscsiop.h
api_name:
- LogoutFromTarget_OUT
targetos: Windows
req.typenames: LogoutFromTarget_OUT, *PLogoutFromTarget_OUT
---

# _LogoutFromTarget_OUT structure


## -description


The LogoutFromTarget_OUT structure holds the output data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logoutfromtarget">LogoutFromTarget</a> method.


## -struct-fields




### -field Status

On output from <b>LogoutFromTarget</b>, the status of the logoff operation. For a list of status qualifiers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.


## -remarks



You must implement this method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/logoutfromtarget">LogoutFromTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_logoutfromtarget_in">LogoutFromTarget_IN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msiscsi-operations-wmi-class">MSiSCSI_Operations WMI Class</a>
 

 

