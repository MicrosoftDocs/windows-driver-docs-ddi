---
UID: NE:extsfns._DEBUG_FLR_PARAM_TYPE
title: _DEBUG_FLR_PARAM_TYPE
author: windows-driver-content
description: The values of DEBUG_FLR_PARAM_TYPE enumeration are tags that indicate the kind of information that is stored in failure analysis entry.
old-location: debugger\debug_flr_param_type.htm
old-project: debugger
ms.assetid: D57D356F-DC11-4C27-97D3-DF40BF2AB490
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DEBUG_FLR_PARAM_TYPE, DEBUG_FLR_PARAM_TYPE, FA_TAG
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
req.alt-api: DEBUG_FLR_PARAM_TYPE
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
req.typenames: DEBUG_FLR_PARAM_TYPE
---

# _DEBUG_FLR_PARAM_TYPE enumeration



## -description
The values of <b>DEBUG_FLR_PARAM_TYPE</b> enumeration are tags that indicate the kind of information that is stored in <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">failure analysis entry</a>.

The <b>DEBUG_FLR_PARAM_TYPE</b> enumeration is also called the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.



## -syntax

````
typedef enum _DEBUG_FLR_PARAM_TYPE { 
  DEBUG_FLR_INVALID        = 0,
  DEBUG_FLR_RESERVED,
  DEBUG_FLR_DRIVER_OBJECT,
  ...,
  DEBUG_FLR_MASK_ALL       = 0xFFFFFFFF
} DEBUG_FLR_PARAM_TYPE;
````


## -enum-fields

### -field DEBUG_FLR_INVALID


### -field DEBUG_FLR_RESERVED


### -field DEBUG_FLR_DRIVER_OBJECT


### -field ...


### -field DEBUG_FLR_MASK_ALL


## -remarks
There are several hundred tags in the <b>DEBUG_FLR_PARAM_TYPE</b> enumeration. You can see all the tags in the extsfns.h header file, which in the Debugging Tools for Windows package.

The tags are grouped by categories, with the first entry of a new category being assigned an explicit value.  For example, the tags that are used for structured data begin with DEBUG_FLR_STACK = 0x200000.

For more information about tags, see <a href="debugger.writing_an_analysis_extension_to_extend__analyze#failure_analysis_entries_tags_and_data_types#failure_analysis_entries_tags_and_data_types">Failure Analysis Entries, Tags, and Data Types</a>


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj991807">Failure Analysis Entries</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG enumeration</a>
</dt>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_FLR_PARAM_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

