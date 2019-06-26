---
UID: NE:extsfns._DEBUG_FAILURE_TYPE
title: _DEBUG_FAILURE_TYPE (extsfns.h)
description: The values in the DEBUG_FAILURE_TYPE enumeration indicate the type of a failure.
old-location: debugger\debug_failure_type.htm
tech.root: debugger
ms.assetid: BFCFE35A-5697-4F9D-B0A1-51EB5D8AE690
ms.date: 05/03/2018
ms.keywords: DEBUG_FAILURE_TYPE, DEBUG_FAILURE_TYPE enumeration [Windows Debugging], DEBUG_FLR_IE_CRASH, DEBUG_FLR_KERNEL, DEBUG_FLR_UNKNOWN, DEBUG_FLR_USER_CRASH, _DEBUG_FAILURE_TYPE, debugger.debug_failure_type, extsfns/DEBUG_FAILURE_TYPE, extsfns/DEBUG_FLR_IE_CRASH, extsfns/DEBUG_FLR_KERNEL, extsfns/DEBUG_FLR_UNKNOWN, extsfns/DEBUG_FLR_USER_CRASH
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
- DEBUG_FAILURE_TYPE
product:
- Windows
targetos: Windows
req.typenames: DEBUG_FAILURE_TYPE
---

# _DEBUG_FAILURE_TYPE enumeration


## -description


The values in the <b>DEBUG_FAILURE_TYPE</b> enumeration indicate the type of a failure.


## -enum-fields




### -field DEBUG_FLR_UNKNOWN

The failure type is not known.


### -field DEBUG_FLR_KERNEL

The failing code was running in kernel mode.


### -field DEBUG_FLR_USER_CRASH

The failing code was running in user mode.


### -field DEBUG_FLR_IE_CRASH

The failure occurred in the application iexplore.exe.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nn-extsfns-idebugfailureanalysis2">IDebugFailureAnalysis2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/extsfns/nc-extsfns-ext_analysis_plugin">_EFN_Analyze</a>
 

 

