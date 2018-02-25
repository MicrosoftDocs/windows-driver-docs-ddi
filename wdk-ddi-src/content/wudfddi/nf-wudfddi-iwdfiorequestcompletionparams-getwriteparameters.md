---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetWriteParameters
title: IWDFIoRequestCompletionParams::GetWriteParameters method
author: windows-driver-content
description: The GetWriteParameters method retrieves parameters that are associated with the completion of a write request.
old-location: wdf\iwdfiorequestcompletionparams_getwriteparameters.htm
old-project: wdf
ms.assetid: 7161ba67-d94a-4f05-bb8f-a97ef418e580
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, C, D, F, G, GetWriteParameters method, GetWriteParameters method, IWDFIoRequestCompletionParams interface, GetWriteParameters,IWDFIoRequestCompletionParams.GetWriteParameters, I, IWDFIoRequestCompletionParams, IWDFIoRequestCompletionParams interface, GetWriteParameters method, IWDFIoRequestCompletionParams::GetWriteParameters, P, R, UMDFRequestObjectRef_018d6259-d6c5-4004-966a-6d18bca94057.xml, W, a, e, i, l, m, n, o, p, q, r, s, t, u, umdf.iwdfiorequestcompletionparams_getwriteparameters, wdf.iwdfiorequestcompletionparams_getwriteparameters, wudfddi/IWDFIoRequestCompletionParams::GetWriteParameters"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFIoRequestCompletionParams.GetWriteParameters
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequestCompletionParams::GetWriteParameters method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetWriteParameters</b> method retrieves parameters that are associated with the completion of a write request.


## -syntax


````
void  GetWriteParameters(
  [out] IWDFMemory **ppWriteMemory,
  [out] SIZE_T     pBytesWritten,
  [out] SIZE_T     pWriteMemoryOffset
);
````


## -parameters




### -param ppWriteMemory [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for access to the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pBytesWritten [out]

A pointer to a variable that receives the size, in bytes, of the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pWriteMemoryOffset [out]

A pointer to a variable that receives the offset, in bytes, into the write buffer for the completion of the write request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns



None




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequestcompletionparams.md">IWDFIoRequestCompletionParams</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequestCompletionParams::GetWriteParameters method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

