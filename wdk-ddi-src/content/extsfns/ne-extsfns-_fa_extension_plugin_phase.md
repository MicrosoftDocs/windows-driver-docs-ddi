---
UID: NE:extsfns._FA_EXTENSION_PLUGIN_PHASE
title: _FA_EXTENSION_PLUGIN_PHASE (extsfns.h)
description: A value in the FA_EXTENSION_PLUGIN_PHASE enumeration is passed to the _EFN_Analyze function to specify which phase of the analysis is currently in progress.
old-location: debugger\fa_extension_plugin_phase.htm
tech.root: debugger
ms.assetid: 67BDC6F7-4099-4AE9-931A-302FDBE1B05C
ms.date: 05/03/2018
ms.keywords: FA_EXTENSION_PLUGIN_PHASE, FA_EXTENSION_PLUGIN_PHASE enumeration [Windows Debugging], FA_PLUGIN_INITILIZATION, FA_PLUGIN_POST_BUCKETING, FA_PLUGIN_PRE_BUCKETING, FA_PLUGIN_STACK_ANALYSIS, _FA_EXTENSION_PLUGIN_PHASE, debugger.fa_extension_plugin_phase, extsfns/FA_EXTENSION_PLUGIN_PHASE, extsfns/FA_PLUGIN_INITILIZATION, extsfns/FA_PLUGIN_POST_BUCKETING, extsfns/FA_PLUGIN_PRE_BUCKETING, extsfns/FA_PLUGIN_STACK_ANALYSIS
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- extsfns.h
api_name:
- FA_EXTENSION_PLUGIN_PHASE
product:
- Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# _FA_EXTENSION_PLUGIN_PHASE enumeration


## -description


A value in the <b>FA_EXTENSION_PLUGIN_PHASE</b> enumeration is passed to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a> function to specify which phase of the analysis is currently in progress.


## -enum-fields




### -field FA_PLUGIN_INITIALIZATION


### -field FA_PLUGIN_STACK_ANALYSIS

The analysis is in the stack analysis phase. This is after the stack is analyzed, and
    the analysis engine has the information, if it was available on the stack, about the faulting symbol and
     module.


### -field FA_PLUGIN_PRE_BUCKETING

The analysis is in the prebucketing phase. This is just before the analysis engine generates a bucket.


### -field FA_PLUGIN_POST_BUCKETING

The analysis is in the post bucketing phase. This is just after the analysis engine generates a bucket.


#### - FA_PLUGIN_INITILIZATION

The analysis is in the initialization phase. This is after the primary data such as
    exception record (for user mode) or  bugcheck code (for kernel
     mode) is initialized.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

