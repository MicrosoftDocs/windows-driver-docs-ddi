---
UID: NN:extsfns.IDebugFailureAnalysis2
title: IDebugFailureAnalysis2 (extsfns.h)
description: When the !analyze debugger command runs, the analysis engine can load and run extension analysis plug-ins.
old-location: debugger\idebugfailureanalysis2.htm
tech.root: debugger
ms.assetid: 0B44FCB9-D23F-4630-9F9A-FBAD46712B14
ms.date: 05/03/2018
keywords: ["IDebugFailureAnalysis2 interface"]
ms.keywords: IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], IDebugFailureAnalysis2 interface [Windows Debugging],described, debugger.idebugfailureanalysis2, extsfns/IDebugFailureAnalysis2
f1_keywords:
 - "extsfns/IDebugFailureAnalysis2"
 - "IDebugFailureAnalysis2"
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
- COM
api_location:
- extsfns.h
api_name:
- IDebugFailureAnalysis2
targetos: Windows
req.typenames: 
---

# IDebugFailureAnalysis2 interface


## -description


When the <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-analyze">!analyze</a> debugger command runs, the analysis engine can load and run extension analysis plug-ins. The analysis engine creates a <i>DebugFailureAnalysis object</i> to organize data that is related to a particular analysis session.

 An extension analysis plug-in can access a DebugFailureAnalysis object through an <b>IDebugFailureAnalysis2</b> interface. The plug-in can inspect, alter, and enhance the information created by the default analysis. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugFailureAnalysis2</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IDebugFailureAnalysis2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/-analyze">!analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

