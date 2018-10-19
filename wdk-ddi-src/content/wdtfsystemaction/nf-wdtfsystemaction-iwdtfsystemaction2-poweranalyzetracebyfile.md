---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.PowerAnalyzeTraceByFile
title: IWDTFSystemAction2::PowerAnalyzeTraceByFile
author: windows-driver-content
description: Analyzes a power trace session that has already been collected and stored in the associated trace message (.etl) log file. This method will only work on Windows 8 and above.
old-location: dtf\iwdtfsystemaction2_poweranalyzetracebyfile.htm
tech.root: dtf
ms.assetid: B8C422C0-7E42-4BE7-8919-A4ABF33E8D5E
ms.date: 04/04/2018
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework],PowerAnalyzeTraceByFile method, IWDTFSystemAction2.PowerAnalyzeTraceByFile, IWDTFSystemAction2::PowerAnalyzeTraceByFile, Microsoft.WDTF.IWDTFSystemAction2.PowerAnalyzeTraceByFile, Microsoft::WDTF::IWDTFSystemAction2::PowerAnalyzeTraceByFile, PowerAnalyzeTraceByFile, PowerAnalyzeTraceByFile method [Windows Device Testing Framework], PowerAnalyzeTraceByFile method [Windows Device Testing Framework],IWDTFSystemAction2 interface, dtf.iwdtfsystemaction2_poweranalyzetracebyfile, wdtfsystemaction/IWDTFSystemAction2::PowerAnalyzeTraceByFile
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.PowerAnalyzeTraceByFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSystemAction2::PowerAnalyzeTraceByFile


## -description


Analyzes a power trace session that has already been collected and stored in the associated trace message (.etl) log file. This method will only 
    work on Windows 8 and above.


## -parameters




### -param EventFilePath [in]

Specifies the location to store the trace message (.etl)
    log file.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>
 

 

