---
UID: NF:wia_lh.IWiaErrorHandler.GetStatusDescription
title: IWiaErrorHandler::GetStatusDescription (wia_lh.h)
description: The system UI calls the GetStatusDescription method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension.
tech.root: image
ms.date: 11/10/2022
keywords: ["IWiaErrorHandler::GetStatusDescription"]
ms.keywords: GetStatusDescription, GetStatusDescription method [Imaging Devices], GetStatusDescription method [Imaging Devices],IWiaErrorHandler interface, IWiaErrorHandler interface [Imaging Devices],GetStatusDescription method, IWiaErrorHandler.GetStatusDescription, IWiaErrorHandler::GetStatusDescription, IWiaErrorHandler_4bd0cba6-d729-4942-b56a-588af88ef913.xml, image.iwiaerrorhandler_getstatusdescription, wia_lh/IWiaErrorHandler::GetStatusDescription
req.header: wia_lh.h
req.include-header: Wia_lh.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWiaErrorHandler::GetStatusDescription
 - wia_lh/IWiaErrorHandler::GetStatusDescription
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wia_lh.h
api_name:
 - IWiaErrorHandler::GetStatusDescription
---

## -description

 The system UI calls the **GetStatusDescription** method to provide the user with extra information about an error, if the user requests this information. This method is implemented by a driver's UI extension.

## -parameters

### -param lFlags [in]

Currently unused. Should be set to zero.

### -param pWiaItem2 [in]

Pointer to the [**IWiaItem2**](/windows/win32/wia/-wia-iwiaitem2) item being transferred.

### -param hrStatus [in]

HRESULT variable that contains the status code received by the WIA transfer method, for example the [**IWiaDataCallback::BandedDataCallback**](/windows/win32/api/wia_xp/nf-wia_xp-iwiadatacallback-bandeddatacallback).

### -param pbstrDescription [out]

Pointer to a BSTR that receives a description of the status or error encountered during the transfer. This parameter cannot be **NULL**. The driver must allocate the string using the [**SysAllocString**](/windows/win32/api/oleauto/nf-oleauto-sysallocstring) function and the caller must free the string using the **SysFreeString**](/windows/win32/api/oleauto/nf-oleauto-sysfreestring) function.

## -returns

Returns a standard COM error code if an error occurs, or one of the following:

| Return code | Description |
|---|---|
| **S_OK** | The *pbstrDescription* parameter contains a valid BSTR pointer. |
| **WIA_STATUS_NOT_HANDLED** | The value in the *hrStatus* parameter is unknown to the extension and no description is available. |

## -remarks

In order for an application to call **IWiaErrorHandler::GetStatusDescription**, the application must call **IWiaItem2::GetExtension** first to receive an interface pointer to the error handling extension. An application must pass "ErrorHandler" as bstrName and IID_IWiaErrorHandler as riidExtensionInterface. An application should pass 0 as lFlags to ensure upward compatibility.

The implementation of **IWiaErrorHandler::GetStatusDescription** should return S_OK for all the device status codes (*hrStatus*) that the implementation of [**IWiaErrorHandler::ReportStatus**](nf-wia_lh-iwiaerrorhandler-reportstatus.md) handles, and WIA_STATUS_NOT_HANDLED for those that **IWiaErrorHandler::ReportStatus** does not handle.

## -see-also

[**IWiaErrorHandler**](nn-wia_lh-iwiaerrorhandler.md)

[**IWiaErrorHandler::ReportStatus**](nf-wia_lh-iwiaerrorhandler-reportstatus.md)
