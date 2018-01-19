---
UID: NS:wdm._COUNTED_REASON_CONTEXT
title: _COUNTED_REASON_CONTEXT
author: windows-driver-content
description: The COUNTED_REASON_CONTEXT structure contains one or more strings that give reasons for a power request.
old-location: kernel\counted_reason_context.htm
old-project: kernel
ms.assetid: beb17d50-d99a-4baf-99bd-9f42fbea0478
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _COUNTED_REASON_CONTEXT, *PCOUNTED_REASON_CONTEXT, COUNTED_REASON_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: COUNTED_REASON_CONTEXT
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: *PCOUNTED_REASON_CONTEXT, COUNTED_REASON_CONTEXT
req.product: Windows 10 or later.
---

# _COUNTED_REASON_CONTEXT structure



## -description
The <b>COUNTED_REASON_CONTEXT</b> structure contains one or more strings that give reasons for a power request.



## -syntax

````
typedef struct _COUNTED_REASON_CONTEXT {
  ULONG Version;
  ULONG Flags;
  union {
    struct {
      UNICODE_STRING  ResourceFileName;
      USHORT          ResourceReasonId;
      ULONG           StringCount;
      PUNICODE_STRING ReasonStrings;
    };
    UNICODE_STRING SimpleString;
  };
} COUNTED_REASON_CONTEXT, *PCOUNTED_REASON_CONTEXT;
````


## -struct-fields

### -field Version

The version number of the structure. Set this member to DIAGNOSTIC_REASON_VERSION.


### -field Flags

Indicates whether the structure contains a simple reason string or a detailed set of reason strings. Set this member to one of the following constants:

<ul>
<li>
DIAGNOSTIC_REASON_SIMPLE_STRING

</li>
<li>
DIAGNOSTIC_REASON_DETAILED_STRING

</li>
</ul>
If <b>Flags</b> = DIAGNOSTIC_REASON_SIMPLE_STRING, the <b>SimpleString</b> member of the union is valid. If <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING, the <b>ResourceFileName</b>, <b>ResourceReasonId</b>, <b>StringCount</b>, and <b>ReasonStrings</b> members are valid (and the <b>SimpleString</b> member is not valid).


### -field ResourceFileName

A pointer to a wide-character, null-terminated string that contains the pathname of a resource file. This resource file contains one or more localized strings that give reasons for a power request. This member is optional and can be specified as <b>NULL</b> or as an empty string if no resource file is required. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING. 


### -field ResourceReasonId

The resource ID assigned to the first reason string in the resource file that is specified by <b>ResourceFileName</b>. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING. 


### -field StringCount

The number of reason strings in the <b>ReasonStrings</b> array or in the resource file that is specified by <b>ResourceFileName</b>. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING. 


### -field ReasonStrings

A pointer to an array of string pointers. Each array element is a pointer to a wide-character, null-terminated string. The number of array elements is specified by <b>StringCount</b>. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING. 


### -field SimpleString

A pointer to a wide-character, null-terminated string that explains the reason for a power request. This member is valid only if <b>Flags</b> = DIAGNOSTIC_REASON_SIMPLE_STRING. 


## -remarks
This structure is used by the <a href="..\ntifs\nf-ntifs-pocreatepowerrequest.md">PoCreatePowerRequest</a> routine.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> uses the reason string or strings contained in this structure as a diagnostic aid during functional and performance testing.

The <b>COUNTED_REASON_CONTEXT</b> structure can contain either a simple reason string or a set of detailed reason strings. If <b>Flags</b> = DIAGNOSTIC_REASON_SIMPLE_STRING, the <b>SimpleString</b> member points to a string that explains the reason for the power request. If <b>Flags</b> = DIAGNOSTIC_REASON_DETAILED_STRING, the <b>ResourceFileName</b>, <b>ResourceReasonId</b>, <b>StringCount</b>, and <b>ReasonStrings</b> members can give a detailed set of reasons for the power request.

The DIAGNOSTIC_REASON_DETAILED_STRING flag supports localization. If the localized resource file specified by <b>ResourceFileName</b> exists, the power manager retrieves a set of resource strings from the file and uses these strings in place of the strings contained in the <b>ReasonStrings</b> array. <b>ResourceId</b> specifies the resource index of the first string in the file to use as a reason string, and <b>StringCount</b> specifies the number of resource strings to use as reason strings. The resource strings must have consecutive resource indexes.


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-pocreatepowerrequest.md">PoCreatePowerRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20COUNTED_REASON_CONTEXT structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

