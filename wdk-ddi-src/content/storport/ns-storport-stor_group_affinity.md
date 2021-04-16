---
UID: NS:storport._STOR_GROUP_AFFINITY
tech.root: storage
title: STOR_GROUP_AFFINITY
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: The STOR_GROUP_AFFINITY structure specifies a group number and the processor affinity within that group.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_GROUP_AFFINITY, *PSTOR_GROUP_AFFINITY
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_GROUP_AFFINITY
 - PSTOR_GROUP_AFFINITY
 - STOR_GROUP_AFFINITY
f1_keywords:
 - _STOR_GROUP_AFFINITY
 - storport/_STOR_GROUP_AFFINITY
 - PSTOR_GROUP_AFFINITY
 - storport/PSTOR_GROUP_AFFINITY
 - STOR_GROUP_AFFINITY
 - storport/STOR_GROUP_AFFINITY
dev_langs:
 - c++
---

## -description

The **STOR_GROUP_AFFINITY** structure specifies a group number and the processor affinity within that group.

## -struct-fields

### -field Mask

A **STOR_AFFINITY** value that specifies the affinity mask. The bits in the affinity mask identify a set of processors within the group identified by **Group**.

### -field Group

Specifies the group number.

### -field Reserved

Reserved for future use. Set all three **Reserved** array elements to zero.

## -remarks

A **STOR_GROUP_AFFINITY** structure describes a thread affinity, which is a set of processors on which a thread is allowed to run. **Mask** contains an affinity mask that identifies the processors in the set. All of the processors in this set belong to the group that is identified by the **Group** member of the structure.

The [**StorPortSetSystemGroupAffinityThread**](nf-storport-storportsetsystemgroupaffinitythread.md) and [**StorPortRevertToUserGroupAffinityThread**](nf-storport-storportreverttousergroupaffinitythread.md) routines use **STOR_GROUP_AFFINITY** structures to specify thread affinities.

## -see-also

[**StorPortRevertToUserGroupAffinityThread**](nf-storport-storportreverttousergroupaffinitythread.md)

[**StorPortSetSystemGroupAffinityThread**](nf-storport-storportsetsystemgroupaffinitythread.md)
