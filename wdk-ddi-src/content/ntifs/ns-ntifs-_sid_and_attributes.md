---
UID: NS:ntifs._SID_AND_ATTRIBUTES
title: _SID_AND_ATTRIBUTES (ntifs.h)
description: The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups.
old-location: ifsk\sid_and_attributes.htm
tech.root: ifsk
ms.assetid: 37c299ab-16a6-4fa2-8ac9-55d75cc98f60
ms.date: 04/16/2018
keywords: ["SID_AND_ATTRIBUTES structure"]
ms.keywords: "*PSID_AND_ATTRIBUTES, PSID_AND_ATTRIBUTES, PSID_AND_ATTRIBUTES structure pointer [Installable File System Drivers], SID_AND_ATTRIBUTES, SID_AND_ATTRIBUTES structure [Installable File System Drivers], _SID_AND_ATTRIBUTES, ifsk.sid_and_attributes, ntifs/PSID_AND_ATTRIBUTES, ntifs/SID_AND_ATTRIBUTES, securitystructures_b0075789-13b6-4324-965b-33a162bff18b.xml"
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
req.typenames: SID_AND_ATTRIBUTES, *PSID_AND_ATTRIBUTES
f1_keywords:
 - _SID_AND_ATTRIBUTES
 - ntifs/_SID_AND_ATTRIBUTES
 - PSID_AND_ATTRIBUTES
 - ntifs/PSID_AND_ATTRIBUTES
 - SID_AND_ATTRIBUTES
 - ntifs/SID_AND_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - SID_AND_ATTRIBUTES
---

# _SID_AND_ATTRIBUTES structure


## -description

The SID_AND_ATTRIBUTES structure represents a security identifier (SID) and its attributes. SIDs are used to uniquely identify users or groups.

## -struct-fields

### -field Sid

Pointer to a SID structure.

### -field Attributes

Specifies attributes of the SID. This value contains up to 32 one-bit flags. Its meaning depends on the definition and use of the SID.

## -remarks

A group is represented by a SID. SIDs have attributes that indicate whether they are currently enabled, disabled, or mandatory, and how they are used. A <b>SID_AND_ATTRIBUTES</b> structure can represent a SID whose attributes change frequently. For example, it is used to represent groups in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/ace">ACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_sid">SID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sefiltertoken">SeFilterToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_token_groups">TOKEN_GROUPS</a>

