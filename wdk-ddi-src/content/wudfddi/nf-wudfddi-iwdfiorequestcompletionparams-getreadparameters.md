---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetReadParameters
title: IWDFIoRequestCompletionParams::GetReadParameters (wudfddi.h)
description: The GetReadParameters method retrieves parameters that are associated with the completion of a read request.
old-location: wdf\iwdfiorequestcompletionparams_getreadparameters.htm
tech.root: wdf
ms.assetid: 8f38616e-498b-485e-84c8-de62477b5871
ms.date: 02/26/2018
ms.keywords: GetReadParameters, GetReadParameters method, GetReadParameters method,IWDFIoRequestCompletionParams interface, IWDFIoRequestCompletionParams interface,GetReadParameters method, IWDFIoRequestCompletionParams.GetReadParameters, IWDFIoRequestCompletionParams::GetReadParameters, UMDFRequestObjectRef_008ca4d6-ddbe-4288-9b5d-d6ccb35518db.xml, umdf.iwdfiorequestcompletionparams_getreadparameters, wdf.iwdfiorequestcompletionparams_getreadparameters, wudfddi/IWDFIoRequestCompletionParams::GetReadParameters
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoRequestCompletionParams.GetReadParameters"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoRequestCompletionParams.GetReadParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequestCompletionParams::GetReadParameters


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetReadParameters</b> method retrieves parameters that are associated with the completion of a read request.


## -parameters




### -param ppReadMemory [out]

A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for access to the read buffer for the completion of the read request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pBytesRead [out]

A pointer to a variable that receives the size, in bytes, of the read buffer for the completion of the read request.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pReadMemoryOffset [out]

A pointer to a variable that receives the offset, in bytes, into the read buffer for the completion of the read request.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequestcompletionparams">IWDFIoRequestCompletionParams</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>
 

 

