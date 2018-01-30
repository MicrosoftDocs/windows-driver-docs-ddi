---
UID: NF:wia_lh.IWiaErrorHandler.GetStatusDescription
title: IWiaErrorHandler::GetStatusDescription method
author: windows-driver-content
description: The system UI calls the GetStatusDescription method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension.
old-location: image\iwiaerrorhandler_getstatusdescription.htm
old-project: image
ms.assetid: c3b5622d-9d51-4008-abb0-c8a60c4a6b16
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IWiaErrorHandler interface [Imaging Devices], GetStatusDescription method, wia_lh/IWiaErrorHandler::GetStatusDescription, IWiaErrorHandler_4bd0cba6-d729-4942-b56a-588af88ef913.xml, GetStatusDescription, GetStatusDescription method [Imaging Devices], IWiaErrorHandler interface, IWiaErrorHandler::GetStatusDescription, GetStatusDescription method [Imaging Devices], IWiaErrorHandler, image.iwiaerrorhandler_getstatusdescription
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: Wia.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: wia_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wia_lh.h
apiname:
-	IWiaErrorHandler.GetStatusDescription
product: Windows
targetos: Windows
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IWiaErrorHandler::GetStatusDescription method


## -description


 The system UI calls the <b>GetStatusDescription</b> method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension.


## -syntax


````
HRESULT GetStatusDescription(
  [in]  LONG      lFlags,
  [in]  IWiaItem2 *pWiaItem2,
  [in]  HRESULT   hrStatus,
  [out] BSTR      *pbstrDescription
);
````


## -parameters




### -param lFlags [in]

Currently unused. Should be set to zero. 


### -param pWiaItem2 [in]

Pointer to the <b>IWiaItem2</b> item being transferred. <b>IWiaItem2</b> is described in the Microsoft Windows SDK documentation.


### -param hrStatus [in]

HRESULT variable that contains the status code received by the WIA transfer method, for example the <b>IWiaDataCallback::BandedDataCallback</b> method (described in the Windows SDK documentation).


### -param pbstrDescription [out]

Pointer to a BSTR that receives a description of the status or error encountered during the transfer. This parameter cannot be <b>NULL</b>. The driver must allocate the string using the <b>SysAllocString</b> function and the caller must free the string using the <b>SysFreeString</b> function. The <b>SysFreeString</b> and <b>SysAllocString </b>functions are described in the Windows SDK documentation.


## -returns


Returns a standard COM error code if an error occurs, or one of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The<i> pbstrDescription</i> parameter contains a valid BSTR pointer.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>WIA_STATUS_NOT_HANDLED</b></dt>
</dl>
</td>
<td width="60%">
The value in the <i>hrStatus</i> parameter is unknown to the extension and no description is available.

</td>
</tr>
</table> 



## -remarks


In order for an application to call <b>IWiaErrorHandler::GetStatusDescription</b>, the application must call <b>IWiaItem2::GetExtension</b> first to receive an interface pointer to the error handling extension. An application must pass "ErrorHandler" as bstrName and IID_IWiaErrorHandler as riidExtensionInterface. An application should pass 0 as lFlags to ensure upward compatibility.

The implementation of <b>IWiaErrorHandler::GetStatusDescription</b> should return S_OK for all the device status codes (<i>hrStatus</i>) that the implementation of <b>IWiaErrorHandler::ReportStatus </b>handles, and WIA_STATUS_NOT_HANDLED for those that <b>IWiaErrorHandler::ReportStatus </b>does not handle.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543909">IWiaErrorHandler::ReportStatus</a>

<a href="..\wia_lh\nn-wia_lh-iwiaerrorhandler.md">IWiaErrorHandler</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaErrorHandler::GetStatusDescription method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

