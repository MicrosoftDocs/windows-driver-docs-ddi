---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetReadParameters
title: IWDFIoRequestCompletionParams::GetReadParameters method
author: windows-driver-content
description: The GetReadParameters method retrieves parameters that are associated with the completion of a read request.
old-location: wdf\iwdfiorequestcompletionparams_getreadparameters.htm
old-project: wdf
ms.assetid: 8f38616e-498b-485e-84c8-de62477b5871
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetReadParameters method, GetReadParameters method, IWDFIoRequestCompletionParams interface, GetReadParameters,IWDFIoRequestCompletionParams.GetReadParameters, IWDFIoRequestCompletionParams, IWDFIoRequestCompletionParams interface, GetReadParameters method, IWDFIoRequestCompletionParams::GetReadParameters, UMDFRequestObjectRef_008ca4d6-ddbe-4288-9b5d-d6ccb35518db.xml, umdf.iwdfiorequestcompletionparams_getreadparameters, wdf.iwdfiorequestcompletionparams_getreadparameters, wudfddi/IWDFIoRequestCompletionParams::GetReadParameters
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequestCompletionParams.GetReadParameters
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequestCompletionParams::GetReadParameters method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetReadParameters</b> method retrieves parameters that are associated with the completion of a read request.


## -syntax


````
void  GetReadParameters(
  [out] IWDFMemory **ppReadMemory,
  [out] SIZE_T     *pBytesRead,
  [out] SIZE_T     *pReadMemoryOffset
);
````


## -parameters




### -param ppReadMemory [out]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for access to the read buffer for the completion of the read request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pBytesRead [out]

A pointer to a variable that receives the size, in bytes, of the read buffer for the completion of the read request.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pReadMemoryOffset [out]

A pointer to a variable that receives the offset, in bytes, into the read buffer for the completion of the read request.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -returns



None




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequestcompletionparams.md">IWDFIoRequestCompletionParams</a>



<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequestCompletionParams::GetReadParameters method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

