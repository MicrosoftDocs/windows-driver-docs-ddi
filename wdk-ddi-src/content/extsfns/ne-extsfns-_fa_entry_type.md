---
UID: NE:extsfns._FA_ENTRY_TYPE
title: _FA_ENTRY_TYPE
author: windows-driver-content
description: A DebugFailureAnalysis object has a collection of failure analysis entries (FA entries).
old-location: debugger\fa_entry_type.htm
old-project: debugger
ms.assetid: 49E0D15E-4214-421F-9C3F-E7C7A481CA10
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _FA_ENTRY_TYPE, FA_ENTRY_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: extsfns.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FA_ENTRY_TYPE
req.alt-loc: extsfns.h
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
req.typenames: FA_ENTRY_TYPE
---

# _FA_ENTRY_TYPE enumeration



## -description
A <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object has a collection of <a href="https://msdn.microsoft.com/library/windows/hardware/jj991807">failure analysis entries</a> (FA entries).  Each FA entry  has a tag, and each tag is associated with one of the data types in the <b>FA_ENTRY_TYPE</b> enumeration. For more information, see <a href="debugger.writing_an_analysis_extension_to_extend__analyze#failure_analysis_entries_tags_and_data_types#failure_analysis_entries_tags_and_data_types">Failure Analysis Entries, Tags, and Data Types</a>.

An FA entry is an <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure along with an optional data block. The data type of the tag indicates the type of data in the data block.



## -syntax

````
typedef enum _FA_ENTRY_TYPE { 
  DEBUG_FA_ENTRY_NO_TYPE,
  DEBUG_FA_ENTRY_ULONG,
  DEBUG_FA_ENTRY_ULONG64,
  DEBUG_FA_ENTRY_INSTRUCTION_OFFSET,
  DEBUG_FA_ENTRY_POINTER,
  DEBUG_FA_ENTRY_ANSI_STRING,
  DEBUG_FA_ENTRY_EXTENSION_CMD,
  DEBUG_FA_ENTRY_STRUCTURED_DATA,
  DEBUG_FA_ENTRY_UNICODE_STRING,
  DEBUG_FA_ENTRY_ARRAY               = 0x8000
} FA_ENTRY_TYPE;
````


## -enum-fields

### -field DEBUG_FA_ENTRY_NO_TYPE

There is no data type associated with the tag, and there is no data block.


### -field DEBUG_FA_ENTRY_ULONG

The data block holds a <b>ULONG</b> value.


### -field DEBUG_FA_ENTRY_ULONG64

The data block holds a <b>ULONG64</b> value.


### -field DEBUG_FA_ENTRY_INSTRUCTION_OFFSET

The data block holds a 64-bit instruction offset.


### -field DEBUG_FA_ENTRY_POINTER

The data block holds a 64-bit pointer.


### -field DEBUG_FA_ENTRY_ANSI_STRING

The data block holds a null-terminated string. The <b>DataSize</b> member of the <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure holds the size of the string including the null terminator.


### -field DEBUG_FA_ENTRY_EXTENSION_CMD

The data block holds a null-terminated string that is a debugger command. An example of a debugger command string is "!analyze -v".


### -field DEBUG_FA_ENTRY_STRUCTURED_DATA

The data block holds a  pointer to an  <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a> interface.


### -field DEBUG_FA_ENTRY_UNICODE_STRING

The data block holds a null-terminated Unicode string. The <b>DataSize</b> member of the <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure holds the size of the Unicode string including the null terminator.


### -field DEBUG_FA_ENTRY_ARRAY

A bitwise OR of this value and one of the basic types indicates an array. For example, if the data type is <b>DEBUG_FA_ENTRY_ARRAY | DEBUG_FA_ENTRY_POINTER</b>, the data block holds an array of pointers. 


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj991807">Failure Analysis Entries</a>
</dt>
<dt>
<a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a>
</dt>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfaentrytags.md">IDebugFAEntryTag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20FA_ENTRY_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

