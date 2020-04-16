---
UID: NF:wudfddi.IWDFIoRequestCompletionParams.GetIoctlParameters
title: IWDFIoRequestCompletionParams::GetIoctlParameters (wudfddi.h)
description: The GetIoctlParameters method retrieves parameters that are associated with the completion of a device I/O control request.
old-location: wdf\iwdfiorequestcompletionparams_getioctlparameters.htm
tech.root: wdf
ms.assetid: 59e2cd27-ec10-46e9-aa0d-4a00e2684e76
ms.date: 02/26/2018
keywords: ["IWDFIoRequestCompletionParams::GetIoctlParameters"]
ms.keywords: GetIoctlParameters, GetIoctlParameters method, GetIoctlParameters method,IWDFIoRequestCompletionParams interface, IWDFIoRequestCompletionParams interface,GetIoctlParameters method, IWDFIoRequestCompletionParams.GetIoctlParameters, IWDFIoRequestCompletionParams::GetIoctlParameters, UMDFRequestObjectRef_7d375866-617c-418f-b449-7931a88e7ae4.xml, umdf.iwdfiorequestcompletionparams_getioctlparameters, wdf.iwdfiorequestcompletionparams_getioctlparameters, wudfddi/IWDFIoRequestCompletionParams::GetIoctlParameters
f1_keywords:
 - "wudfddi/IWDFIoRequestCompletionParams.GetIoctlParameters"
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
- IWDFIoRequestCompletionParams.GetIoctlParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoRequestCompletionParams::GetIoctlParameters


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetIoctlParameters</b> method retrieves parameters that are associated with the completion of a device I/O control request.


## -parameters




### -param pIoControlCode [out, optional]

A pointer to a variable that receives the control code that identifies the specific operation to be performed. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param ppInputMemory [out, optional]

A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for access to the input buffer for the completion of the device I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pInputMemoryOffset [out, optional]

A pointer to a variable that receives the offset, in bytes, into the input buffer for the completion of the I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param ppOutputMemory [out, optional]

A pointer to a variable that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for access to the output buffer for the completion of the device I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pOutputMemoryOffset [out, optional]

A pointer to a variable that receives the offset, in bytes, into the output buffer for the completion of the I/O control request. 

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


### -param pOutBytes [out, optional]

A pointer to a variable that receives the number of bytes that are output for the completion of the device I/O control request.

This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require the information. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequestcompletionparams">IWDFIoRequestCompletionParams</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>
 

 

