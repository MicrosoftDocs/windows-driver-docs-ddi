---
UID: NF:wudfddi.IWDFIoRequest.Impersonate
title: IWDFIoRequest::Impersonate method
author: windows-driver-content
description: The Impersonate method registers the interface for the method that the framework should call for impersonation.
old-location: wdf\iwdfiorequest_impersonate.htm
old-project: wdf
ms.assetid: beb630e7-9667-4bc2-bf35-69db6cf0b104
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoRequest, IWDFIoRequest interface, Impersonate method, IWDFIoRequest::Impersonate, Impersonate method, Impersonate method, IWDFIoRequest interface, Impersonate,IWDFIoRequest.Impersonate, UMDFRequestObjectRef_a5f40359-edc8-42e1-a63d-99390abeba86.xml, umdf.iwdfiorequest_impersonate, wdf.iwdfiorequest_impersonate, wudfddi/IWDFIoRequest::Impersonate
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
-	IWDFIoRequest.Impersonate
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::Impersonate method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Impersonate</b> method registers the interface for the method that the framework should call for impersonation.


## -parameters




### -param ImpersonationLevel [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>-typed value that identifies the level of impersonation.


### -param pCallback [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554912">IImpersonateCallback</a> interface whose method the framework calls for impersonation.


### -param pvCallbackContext [in, optional]

A pointer to a buffer that contains context information that is related to the impersonation call. The framework passes this context information in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a> method. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to supply a context. 


## -returns



<b>Impersonate</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



For information about how UMDF and UMDF drivers handle impersonation, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Impersonation</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554912">IImpersonateCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556631">SECURITY_IMPERSONATION_LEVEL</a>
 

 

