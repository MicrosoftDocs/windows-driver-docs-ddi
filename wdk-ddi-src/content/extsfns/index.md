---
UID: NA:extsfns
ms.assetid: 65a44f62-6646-38b2-b962-e5ad09608ad4
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Extsfns.h header



This header is used by Debugger. For more information, see
- [Debugger](../_debugger/index.md)

Extsfns.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EXT_ANALYSIS_PLUGIN callback](nc-extsfns-ext_analysis_plugin.md) | When you write an Analysis Extension, you must implement and export an EXT_ANALYSIS_PLUGIN (_EFN_Analyze) function. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_FA_ENTRY structure](ns-extsfns-_fa_entry.md) | A DebugFailureAnalysis object has a collection of failure analysis entries (FA entries). Each FA entry is represented by an FA_ENTRY structure. For more information, see Failure Analysis Entries, Tags, and Data Types. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_DEBUG_FAILURE_TYPE enumeration](ne-extsfns-_debug_failure_type.md) | The values in the DEBUG_FAILURE_TYPE enumeration indicate the type of a failure. |
| [_DEBUG_FLR_PARAM_TYPE enumeration](ne-extsfns-_debug_flr_param_type.md) | The values of DEBUG_FLR_PARAM_TYPE enumeration are tags that indicate the kind of information that is stored in failure analysis entry. |
| [_FA_ENTRY_TYPE enumeration](ne-extsfns-_fa_entry_type.md) | A DebugFailureAnalysis object has a collection of failure analysis entries (FA entries). |
| [_FA_EXTENSION_PLUGIN_PHASE enumeration](ne-extsfns-_fa_extension_plugin_phase.md) | A value in the FA_EXTENSION_PLUGIN_PHASE enumeration is passed to the _EFN_Analyze function to specify which phase of the analysis is currently in progress. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IDebugFAEntryTags interface](nn-extsfns-idebugfaentrytags.md) | When the !analyze debugger command runs, the analysis engine can load and run extension analysis plug-ins. |
| [IDebugFailureAnalysis2 interface](nn-extsfns-idebugfailureanalysis2.md) | When the !analyze debugger command runs, the analysis engine can load and run extension analysis plug-ins. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IDebugFAEntryTags::GetProperties method](nf-extsfns-idebugfaentrytags-getproperties.md) | The GetProperties method gets the name or description (or both) of a tag in a DebugFailureAnalysisTags object. |
| [IDebugFAEntryTags::GetTagByName method](nf-extsfns-idebugfaentrytags-gettagbyname.md) | The GetTagByName method searches for a tag that has a specified name. |
| [IDebugFAEntryTags::GetType method](nf-extsfns-idebugfaentrytags-gettype.md) | The GetType method gets the data type that is associated with a tag in a DebugFailureAnalysisTags object. |
| [IDebugFAEntryTags::IsValidTagToSet method](nf-extsfns-idebugfaentrytags-isvalidtagtoset.md) | The IsValidTagToSet method determines whether it is OK to set the data of a specified tag. |
| [IDebugFAEntryTags::SetProperties method](nf-extsfns-idebugfaentrytags-setproperties.md) | The SetProperties method sets the name or description (or both) of a tag in a DebugFailureAnalysisTags object. |
| [IDebugFAEntryTags::SetType method](nf-extsfns-idebugfaentrytags-settype.md) | The SetType method sets the data type that is associated with a tag in a DebugFailureAnalysisTags object. |
| [IDebugFailureAnalysis2::AddBuffer method](nf-extsfns-idebugfailureanalysis2-addbuffer.md) | The AddBuffer method adds a new FA entry to a DebugFailureAnalysis object, and writes the bytes from a specified buffer to the data block of the new FA entry. |
| [IDebugFailureAnalysis2::AddExtensionCommand method](nf-extsfns-idebugfailureanalysis2-addextensioncommand.md) | The AddExtensionCommand method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified debugger command. |
| [IDebugFailureAnalysis2::AddString method](nf-extsfns-idebugfailureanalysis2-addstring.md) | The AddString method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified string. |
| [IDebugFailureAnalysis2::AddUlong method](nf-extsfns-idebugfailureanalysis2-addulong.md) | The AddUlong method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified ULONG value. |
| [IDebugFailureAnalysis2::AddUlong64 method](nf-extsfns-idebugfailureanalysis2-addulong64.md) | The AddUlong64 method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified 64-bit value. |
| [IDebugFailureAnalysis2::Get method](nf-extsfns-idebugfailureanalysis2-get.md) | The Get method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. |
| [IDebugFailureAnalysis2::GetBuffer method](nf-extsfns-idebugfailureanalysis2-getbuffer.md) | The GetBuffer method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block. |
| [IDebugFailureAnalysis2::GetDebugFATagControl method](nf-extsfns-idebugfailureanalysis2-getdebugfatagcontrol.md) | The GetDebugFATagControl method gets a pointer to an IDebugFAEntryTags interface, which provides access to the tags in a DebugFailureAnalysisTags object. |
| [IDebugFailureAnalysis2::GetFailureClass method](nf-extsfns-idebugfailureanalysis2-getfailureclass.md) | The GetFailureClass method gets the failure class of a DebugFailureAnalysis object. The failure class indicates whether the debugging session that created the DebugFailureAnalysis object is a kernel mode session or a user mode session. |
| [IDebugFailureAnalysis2::GetFailureCode method](nf-extsfns-idebugfailureanalysis2-getfailurecode.md) | The GetFailureCode method gets the bug check code or exception code of a DebugFailureAnalysis object. |
| [IDebugFailureAnalysis2::GetFailureType method](nf-extsfns-idebugfailureanalysis2-getfailuretype.md) | The GetFailureType method gets the failure type of a DebugFailureAnalysis object. The failure type indicates whether the code being analyzed was running in kernel mode or user mode. |
| [IDebugFailureAnalysis2::GetNext method](nf-extsfns-idebugfailureanalysis2-getnext.md) | The GetNext method searches a DebugFailureAnalysis object for the next FA entry, after a given FA entry, that satisfies conditions specified by the Tag and TagMask parameters. |
| [IDebugFailureAnalysis2::GetString method](nf-extsfns-idebugfailureanalysis2-getstring.md) | The GetString method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the ANSI string value from the entry's data block. |
| [IDebugFailureAnalysis2::GetUlong method](nf-extsfns-idebugfailureanalysis2-getulong.md) | The GetUlong method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the ULONG value from the entry's data block. |
| [IDebugFailureAnalysis2::GetUlong64 method](nf-extsfns-idebugfailureanalysis2-getulong64.md) | The GetUlong64 method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the ULONG64 value from the entry's data block. |
| [IDebugFailureAnalysis2::NextEntry method](nf-extsfns-idebugfailureanalysis2-nextentry.md) | The NextEntry method gets the next FA entry, after a given FA entry, in a DebugFailureAnalysis object. |
| [IDebugFailureAnalysis2::SetBuffer method](nf-extsfns-idebugfailureanalysis2-setbuffer.md) | The SetBuffer method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it overwrites the data block of the FA entry with the bytes in a specified buffer. |
| [IDebugFailureAnalysis2::SetExtensionCommand method](nf-extsfns-idebugfailureanalysis2-setextensioncommand.md) | The SetExtensionCommand method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. |
| [IDebugFailureAnalysis2::SetString method](nf-extsfns-idebugfailureanalysis2-setstring.md) | The SetString method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified string value. |
| [IDebugFailureAnalysis2::SetUlong method](nf-extsfns-idebugfailureanalysis2-setulong.md) | The SetUlong method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified ULONG value. |
| [IDebugFailureAnalysis2::SetUlong64 method](nf-extsfns-idebugfailureanalysis2-setulong64.md) | The SetUlong64 method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified ULONG64 value. |
