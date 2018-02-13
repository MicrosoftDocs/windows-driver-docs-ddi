---
UID: NF:extsfns.IDebugFailureAnalysis2.GetBuffer
title: IDebugFailureAnalysis2::GetBuffer method
author: windows-driver-content
description: The GetBuffer method searches a DebugFailureAnalysis object for the first FA entry that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.
old-location: debugger\idebugfailureanalysis2_getbuffer.htm
old-project: debugger
ms.assetid: 262B5237-86BF-43D6-A29A-A868663EA5D9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.idebugfailureanalysis2_getbuffer, GetBuffer, GetBuffer method [Windows Debugging], GetBuffer method [Windows Debugging], IDebugFailureAnalysis2 interface, IDebugFailureAnalysis2 interface [Windows Debugging], GetBuffer method, extsfns/IDebugFailureAnalysis2::GetBuffer, IDebugFailureAnalysis2::GetBuffer, IDebugFailureAnalysis2
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
req.lib: extsfns.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	extsfns.h
apiname:
-	IDebugFailureAnalysis2.GetBuffer
product: Windows
targetos: Windows
req.typenames: FA_EXTENSION_PLUGIN_PHASE
---

# IDebugFailureAnalysis2::GetBuffer method


## -description


The <b>GetBuffer</b> method searches a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object for the first <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> that has a specified tag. If it finds an FA entry with the specified tag, it gets the entry's data block.


## -syntax


````
PFA_ENTRY GetBuffer(
  [in]  FA_TAG Tag,
  [out] PVOID  Buf,
  [in]  ULONG  Size
);
````


## -parameters




### -param Tag [in]

A value in the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/writing-an-analysis-extension-to-extend--analyze">FA_TAG</a> enumeration.


### -param Buf [out]

A pointer to a buffer that receives the entry's data block.


### -param Size [in]

The size, in bytes, of the buffer pointed to by <i>Buf</i>.


## -returns



If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, and if it succeeds in getting the data block, it returns a pointer to the <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure. Otherwise, it returns <b>NULL</b>.




## -remarks



If this method finds an <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a> with the specified tag, it checks to see whether the <b>DataSize</b> member of the <a href="..\extsfns\ns-extsfns-_fa_entry.md">FA_ENTRY</a> structure is equal to the value specified by the <i>Size</i> parameter. If <b>DataSize</b> is not equal to <i>Size</i>, this method returns <b>NULL</b> and does not get the data block.




## -see-also

<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>



<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983423">SetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983406">AddBuffer</a>



<a href="..\extsfns\nc-extsfns-ext_analysis_plugin.md">_EFN_Analyze</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::GetBuffer method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

