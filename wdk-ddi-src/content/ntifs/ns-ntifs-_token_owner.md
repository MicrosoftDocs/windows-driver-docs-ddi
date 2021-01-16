---
UID: NS:ntifs._TOKEN_OWNER
title: _TOKEN_OWNER (ntifs.h)
description: TOKEN_OWNER contains the default owner security identifier (SID) that will be applied to newly created objects.
old-location: ifsk\token_owner.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["TOKEN_OWNER structure"]
ms.keywords: "*PTOKEN_OWNER, PTOKEN_OWNER, PTOKEN_OWNER structure pointer [Installable File System Drivers], TOKEN_OWNER, TOKEN_OWNER structure [Installable File System Drivers], _TOKEN_OWNER, ifsk.token_owner, ntifs/PTOKEN_OWNER, ntifs/TOKEN_OWNER, securitystructures_1be454bb-1b55-4fe5-bdbb-85bfcf9dc9c8.xml"
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.typenames: TOKEN_OWNER, *PTOKEN_OWNER
f1_keywords:
 - _TOKEN_OWNER
 - ntifs/_TOKEN_OWNER
 - PTOKEN_OWNER
 - ntifs/PTOKEN_OWNER
 - TOKEN_OWNER
 - ntifs/TOKEN_OWNER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _TOKEN_OWNER
 - PTOKEN_OWNER
 - TOKEN_OWNER
---

# _TOKEN_OWNER structure


## -description

TOKEN_OWNER contains the default owner security identifier (SID) that will be applied to newly created objects.

## -struct-fields

### -field Owner

Pointer to a SID structure representing a user that will become the default owner of any objects created by a process using this access token. The SID must be one of the user or group SIDs already in the token.

## -remarks

Whenever the process using this access token creates a new object, the object is owned by the <b>Owner</b>, unless the process provides a security descriptor for the object. 

The <b>Owner</b> must be a legally formed SID and must match one of the user or group SIDs already in the token. 

If it is a group SID, the <b>Owner</b> must match a group SID in the token, where the attributes on the group must include SE_GROUP_OWNER and must not include SE_GROUP_USE_FOR_DENY_ONLY.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ne-ntifs-_token_information_class">TOKEN_INFORMATION_CLASS</a>



<a href="/previous-versions/ff567055(v=vs.85)">ZwQueryInformationToken</a>



<a href="/previous-versions/ff567102(v=vs.85)">ZwSetInformationToken</a>

