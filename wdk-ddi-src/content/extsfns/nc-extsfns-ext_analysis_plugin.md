---
UID: NC:extsfns.EXT_ANALYSIS_PLUGIN
title: EXT_ANALYSIS_PLUGIN
author: windows-driver-content
description: When you write an Analysis Extension, you must implement and export an EXT_ANALYSIS_PLUGIN (_EFN_Analyze) function.
old-location: debugger\_efn_analyze.htm
old-project: debugger
ms.assetid: 8D7FB040-871F-4F31-83E3-BAD7584C0589
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EXT_ANALYSIS_PLUGIN, _EFN_Analyze, _EFN_Analyze function [Windows Debugging], debugger._efn_analyze, extsfns/_EFN_Analyze
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	extsfns.h
apiname:
-	_EFN_Analyze
product: Windows
targetos: Windows
req.typenames: EVENT_TRACE_HEADER, *PEVENT_TRACE_HEADER
---

# EXT_ANALYSIS_PLUGIN callback


## -description


When you write an <a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Analysis Extension</a>, you must implement and export an <b>EXT_ANALYSIS_PLUGIN</b> (<b>_EFN_Analyze</b>) function. When the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562112">!analyze</a> debugger command runs, it calls your <b>_EFN_Analyze</b> so that you can participate in the analysis of a bug check or exception.


## -prototype


````
HRESULT _EFN_Analyze(
  _In_ PDEBUG_CLIENT4            Client,
  _In_ FA_EXTENSION_PLUGIN_PHASE CallPhase,
  _In_ PDEBUG_FAILURE_ANALYSIS2  pAnalysis
);
````


## -parameters




### -param Client [in]

A pointer to an <a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a> interface.


### -param CallPhase [in]

A value in the <a href="..\extsfns\ne-extsfns-_fa_extension_plugin_phase.md">FA_EXTENSION_PLUGIN_PHASE</a> enumeration that specifies which phase of the analysis is currently in progress. Analysis phases include initialization, stack analysis, prebucketing, and post bucketing.


### -param pAnalysis [in]

A pointer to a <b>IDebugFailureAnalysis2</b> interface.


## -returns



If the function succeeds, return <b>S_OK</b>.




## -see-also

<a href="https://msdn.microsoft.com/45D4E287-ACDB-4479-892F-FCE2287758BA">Writing Custom Analysis Debugger Extension</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20EXT_ANALYSIS_PLUGIN function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

