---
UID: NF:wudfusb.IWDFUsbRequestCompletionParams.GetPipeReadParameters
title: IWDFUsbRequestCompletionParams::GetPipeReadParameters method
author: windows-driver-content
description: The GetPipeReadParameters method retrieves parameters that are associated with the completion of a read request.
old-location: wdf\iwdfusbrequestcompletionparams_getpipereadparameters.htm
old-project: wdf
ms.assetid: e5e3dfa0-49cc-4c2d-828e-fa5c95d3db8c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetPipeReadParameters method, GetPipeReadParameters method, IWDFUsbRequestCompletionParams interface, GetPipeReadParameters,IWDFUsbRequestCompletionParams.GetPipeReadParameters, IWDFUsbRequestCompletionParams, IWDFUsbRequestCompletionParams interface, GetPipeReadParameters method, IWDFUsbRequestCompletionParams::GetPipeReadParameters, UMDFRequestObjectRef_d98f8b7f-c264-4044-aaef-893c717be50a.xml, umdf.iwdfusbrequestcompletionparams_getpipereadparameters, wdf.iwdfusbrequestcompletionparams_getpipereadparameters, wudfusb/IWDFUsbRequestCompletionParams::GetPipeReadParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfusb.h
req.include-header: Wudfusb.h
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
-	IWDFUsbRequestCompletionParams.GetPipeReadParameters
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbRequestCompletionParams::GetPipeReadParameters method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetPipeReadParameters</b> method retrieves parameters that are associated with the completion of a read request.


## -syntax


````
void GetPipeReadParameters(
  [out, optional] IWDFMemory **ppReadMemory,
  [out, optional] SIZE_T     *pBytesRead,
  [out, optional] SIZE_T     *pReadMemoryOffset
);
````


## -parameters




### -param ppReadMemory [out, optional]

A pointer to a variable that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface, for access to the read buffer for the read request. This parameter is optional and can be <b>NULL</b>.


### -param pBytesRead [out, optional]

A pointer to a variable that receives the size, in bytes, of the read buffer for the read request. This parameter is optional and can be <b>NULL</b>.


### -param pReadMemoryOffset [out, optional]

A pointer to a variable that receives the offset, in bytes, into the read buffer for the read request. This parameter is optional and can be <b>NULL</b>.


## -returns



None




## -see-also

<a href="..\wudfusb\nn-wudfusb-iwdfusbrequestcompletionparams.md">IWDFUsbRequestCompletionParams</a>



<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>



 

 


