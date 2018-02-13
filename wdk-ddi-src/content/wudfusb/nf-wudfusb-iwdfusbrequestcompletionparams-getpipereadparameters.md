---
UID: NF:wudfusb.IWDFUsbRequestCompletionParams.GetPipeReadParameters
title: IWDFUsbRequestCompletionParams::GetPipeReadParameters method
author: windows-driver-content
description: The GetPipeReadParameters method retrieves parameters that are associated with the completion of a read request.
old-location: wdf\iwdfusbrequestcompletionparams_getpipereadparameters.htm
old-project: wdf
ms.assetid: e5e3dfa0-49cc-4c2d-828e-fa5c95d3db8c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: umdf.iwdfusbrequestcompletionparams_getpipereadparameters, GetPipeReadParameters method, IWDFUsbRequestCompletionParams interface, UMDFRequestObjectRef_d98f8b7f-c264-4044-aaef-893c717be50a.xml, wudfusb/IWDFUsbRequestCompletionParams::GetPipeReadParameters, IWDFUsbRequestCompletionParams, IWDFUsbRequestCompletionParams::GetPipeReadParameters, GetPipeReadParameters, GetPipeReadParameters method, IWDFUsbRequestCompletionParams interface, GetPipeReadParameters method, wdf.iwdfusbrequestcompletionparams_getpipereadparameters
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
req.lib: wudfusb.h
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
-	IWDFUsbRequestCompletionParams.GetPipeReadParameters
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbRequestCompletionParams::GetPipeReadParameters method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

