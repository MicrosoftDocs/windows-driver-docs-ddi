---
UID: NE:extsfns._FA_ENTRY_TYPE
title: "_FA_ENTRY_TYPE"
author: windows-driver-content
description: A DebugFailureAnalysis object has a collection of failure analysis entries (FA entries).
old-location: debugger\fa_entry_type.htm
tech.root: debugger
ms.assetid: 49E0D15E-4214-421F-9C3F-E7C7A481CA10
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: DEBUG_FA_ENTRY_ANSI_STRING, DEBUG_FA_ENTRY_ARRAY, DEBUG_FA_ENTRY_EXTENSION_CMD, DEBUG_FA_ENTRY_INSTRUCTION_OFFSET, DEBUG_FA_ENTRY_NO_TYPE, DEBUG_FA_ENTRY_POINTER, DEBUG_FA_ENTRY_STRUCTURED_DATA, DEBUG_FA_ENTRY_ULONG, DEBUG_FA_ENTRY_ULONG64, DEBUG_FA_ENTRY_UNICODE_STRING, FA_ENTRY_TYPE, FA_ENTRY_TYPE enumeration [Windows Debugging], _FA_ENTRY_TYPE, debugger.fa_entry_type, extsfns/DEBUG_FA_ENTRY_ANSI_STRING, extsfns/DEBUG_FA_ENTRY_ARRAY, extsfns/DEBUG_FA_ENTRY_EXTENSION_CMD, extsfns/DEBUG_FA_ENTRY_INSTRUCTION_OFFSET, extsfns/DEBUG_FA_ENTRY_NO_TYPE, extsfns/DEBUG_FA_ENTRY_POINTER, extsfns/DEBUG_FA_ENTRY_STRUCTURED_DATA, extsfns/DEBUG_FA_ENTRY_ULONG, extsfns/DEBUG_FA_ENTRY_ULONG64, extsfns/DEBUG_FA_ENTRY_UNICODE_STRING, extsfns/FA_ENTRY_TYPE
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
-	extsfns.h
api_name:
-	FA_ENTRY_TYPE
product:
- Windows
targetos: Windows
req.typenames: FA_ENTRY_TYPE
---

# _FA_ENTRY_TYPE enumeration


## -description


A <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object has a collection of <a href="https://msdn.microsoft.com/library/windows/hardware/jj991807">failure analysis entries</a> (FA entries).  Each FA entry  has a tag, and each tag is associated with one of the data types in the <b>FA_ENTRY_TYPE</b> enumeration. For more information, see <a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Failure Analysis Entries, Tags, and Data Types</a>.

An FA entry is an <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure along with an optional data block. The data type of the tag indicates the type of data in the data block.


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

The data block holds a null-terminated string. The <b>DataSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure holds the size of the string including the null terminator.


### -field DEBUG_FA_ENTRY_ANSI_STRINGs


### -field DEBUG_FA_ENTRY_EXTENSION_CMD

The data block holds a null-terminated string that is a debugger command. An example of a debugger command string is "!analyze -v".


### -field DEBUG_FA_ENTRY_STRUCTURED_DATA

The data block holds a  pointer to an  <a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a> interface.


### -field DEBUG_FA_ENTRY_UNICODE_STRING

The data block holds a null-terminated Unicode string. The <b>DataSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure holds the size of the Unicode string including the null terminator.


### -field DEBUG_FA_ENTRY_ARRAY

A bitwise OR of this value and one of the basic types indicates an array. For example, if the data type is <b>DEBUG_FA_ENTRY_ARRAY | DEBUG_FA_ENTRY_POINTER</b>, the data block holds an array of pointers. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj991807">Failure Analysis Entries</a>



<a href="https://msdn.microsoft.com/B52DFB0E-0035-40C2-B2F5-5E16B16931C2">IDebugFAEntryTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
 

 

