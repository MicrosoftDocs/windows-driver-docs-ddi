---
UID: NS:iscsiop._LogoutFromTarget_IN
title: _LogoutFromTarget_IN (iscsiop.h)
description: The LogoutFromTarget_IN structure holds the input data for the LogoutFromTarget method, which is used to log out from an iSCSI target.
old-location: storage\logoutfromtarget_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["LogoutFromTarget_IN structure"]
ms.keywords: "*PLogoutFromTarget_IN, LogoutFromTarget_IN, LogoutFromTarget_IN structure [Storage Devices], PLogoutFromTarget_IN, PLogoutFromTarget_IN structure pointer [Storage Devices], _LogoutFromTarget_IN, iscsiop/LogoutFromTarget_IN, iscsiop/PLogoutFromTarget_IN, storage.logoutfromtarget_in, structs-iSCSI_759c2265-5518-4f45-8737-5cdfa4d73170.xml"
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
targetos: Windows
req.typenames: LogoutFromTarget_IN, *PLogoutFromTarget_IN
f1_keywords:
 - _LogoutFromTarget_IN
 - iscsiop/_LogoutFromTarget_IN
 - PLogoutFromTarget_IN
 - iscsiop/PLogoutFromTarget_IN
 - LogoutFromTarget_IN
 - iscsiop/LogoutFromTarget_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - _LogoutFromTarget_IN
 - PLogoutFromTarget_IN
 - LogoutFromTarget_IN
---

# _LogoutFromTarget_IN structure


## -description

The LogoutFromTarget_IN structure holds the input data for the <a href="/windows-hardware/drivers/storage/logoutfromtarget">LogoutFromTarget</a> method, which is used to log out from an iSCSI target.

## -struct-fields

### -field UniqueSessionId

A 64-bit integer that uniquely identifies the session. The <a href="/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a> and <a href="/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a> methods both return this value in the <i>UniqueSessionId</i> parameter. Do not confuse this value with the values in the ISID and TSID members.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/addconnectiontosession">AddConnectionToSession</a>



<a href="/windows-hardware/drivers/storage/logintotarget">LoginToTarget</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_logoutfromtarget_out">LogoutFromTarget_OUT</a>



<a href="/windows-hardware/drivers/storage/msiscsi-operations-wmi-class">MSiSCSI_Operations WMI Class</a>

