---
UID: NC:extsfns.EXT_ANALYSIS_PLUGIN
title: EXT_ANALYSIS_PLUGIN (extsfns.h)
description: When you write an Analysis Extension, you must implement and export an EXT_ANALYSIS_PLUGIN (_EFN_Analyze) function.
old-location: debugger\_efn_analyze.htm
tech.root: debugger
ms.date: 12/16/2021
keywords: ["EXT_ANALYSIS_PLUGIN callback function"]
ms.keywords: EXT_ANALYSIS_PLUGIN, EXT_ANALYSIS_PLUGIN callback, _EFN_Analyze, _EFN_Analyze callback function [Windows Debugging], debugger._efn_analyze, extsfns/_EFN_Analyze
req.header: extsfns.h
req.include-header: 
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - EXT_ANALYSIS_PLUGIN
 - extsfns/EXT_ANALYSIS_PLUGIN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - extsfns.h
api_name:
 - EXT_ANALYSIS_PLUGIN
---

# EXT_ANALYSIS_PLUGIN callback function


## -description

When you write an <a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Analysis Extension</a>, you must implement an <b>EXT_ANALYSIS_PLUGIN</b> exported as (<b>_EFN_Analyze</b>). When the <a href="/windows-hardware/drivers/debugger/-analyze">!analyze</a> debugger command runs, it calls your <b>_EFN_Analyze</b> in each phase, so that you can participate in the analysis.

The WINAPI (__stdcall) calling convention is required. No exceptions (noexcept) should leave the function.

## -parameters

### -param Client [in]

A pointer to an <a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugclient4">IDebugClient4</a> interface. Use this interface to access the debugger. Use QueryInterface to access other Debugger interfaces, such as the Legacy (`IDebug*`), Debug Host (`IDebugHost*`), Data Model (`IDataModel*`), etc., interfaces.

### -param CallPhase [in]


A value in the <a href="/windows-hardware/drivers/ddi/extsfns/ne-extsfns-_fa_extension_plugin_phase">FA_EXTENSION_PLUGIN_PHASE</a> enumeration that specifies which phase of the analysis is currently in progress. Analysis phases include initialization, stack analysis, pre-bucketing, and post-bucketing.

### -param pAnalysis [in]

A pointer to a <b>IDebugFailureAnalysis2</b> interface. Use this interface to Get/Set properties of the analysis. Use QueryInterface to access other !analyze interfaces.

## -returns

<b>S_OK</b> – A change was made.

<b>S_FALSE</b> – No changes were made.

<b>E_*</b> - An error occurred. !analyze will report the error via Key/Value using a Key string of “Plugin.Exception.<Phase>.<DLL>” and Value string of the HRESULT in “0x%08x” format.



## -see-also

<a href="/windows-hardware/drivers/debugger/writing-custom-analysis-debugger-extensions">Writing Custom Analysis Debugger Extension</a>



<a href="/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>

