---
UID: NF:extsfns.IDebugFailureAnalysis2.SetUlong
title: IDebugFailureAnalysis2::SetUlong method
author: windows-driver-content
description: The SetUlong method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified ULONG value.
old-location: debugger\idebugfailureanalysis2_setulong.htm
old-project: debugger
ms.assetid: 90C0AAE1-EE79-4347-B6F1-276DBF84F7BC
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugFailureAnalysis2, IDebugFailureAnalysis2 interface [Windows Debugging], SetUlong method, IDebugFailureAnalysis2::SetUlong, SetUlong method [Windows Debugging], SetUlong method [Windows Debugging], IDebugFailureAnalysis2 interface, SetUlong,IDebugFailureAnalysis2.SetUlong, debugger.idebugfailureanalysis2_setextensionulong, debugger.idebugfailureanalysis2_setulong, extsfns/IDebugFailureAnalysis2::SetUlong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	extsfns.h
api_name:
-	IDebugFailureAnalysis2.SetUlong
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::SetUlong method


## -description


The <b>SetUlong</b> method searches a <a href="https://msdn.microsoft.com/0B44FCB9-D23F-4630-9F9A-FBAD46712B14">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it sets (overwrites) the data block of the FA entry to a specified <b>ULONG</b> value. If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has the specified tag, it creates a new FA entry with that tag and sets the data block of the new FA entry to the specified <b>ULONG</b> value.


## -parameters




### -param Tag

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param Value [in]

The <b>ULONG</b> value to be written to the data block of the new or existing <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.


## -returns



If this method succeeds, it returns a pointer to the new or existing <a href="https://msdn.microsoft.com/library/windows/hardware/jj991808">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the data type associated with that tag is <b>DEBUG_FA_ENTRY_ULONG</b>. If the data type associated with the tag is not <b>DEBUG_FA_ENTRY_ULONG</b>, this method returns NULL and does not overwrite the entry's data block.

If this method does not find an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it creates a new FA entry with that tag, and it associates the tag with the data type  <b>DEBUG_FA_ENTRY_ULONG</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj983409">AddUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983420">GetUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983405">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983432">_EFN_Analyze</a>
 

 

