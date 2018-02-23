---
UID: NF:wudfddi.IWDFIoRequest.Impersonate
title: IWDFIoRequest::Impersonate method
author: windows-driver-content
description: The Impersonate method registers the interface for the method that the framework should call for impersonation.
old-location: wdf\iwdfiorequest_impersonate.htm
old-project: wdf
ms.assetid: beb630e7-9667-4bc2-bf35-69db6cf0b104
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: Impersonate, Impersonate method, IWDFIoRequest interface, wdf.iwdfiorequest_impersonate, wudfddi/IWDFIoRequest::Impersonate, UMDFRequestObjectRef_a5f40359-edc8-42e1-a63d-99390abeba86.xml, Impersonate method, IWDFIoRequest::Impersonate, IWDFIoRequest, IWDFIoRequest interface, Impersonate method, umdf.iwdfiorequest_impersonate
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
-	IWDFIoRequest.Impersonate
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest::Impersonate method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Impersonate</b> method registers the interface for the method that the framework should call for impersonation.


## -syntax


````
HRESULT Impersonate(
  [in]           SECURITY_IMPERSONATION_LEVEL ImpersonationLevel,
  [in]           IImpersonateCallback         *pCallback,
  [in, optional] void                         *pvCallbackContext
);
````


## -parameters




### -param ImpersonationLevel [in]

A <a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>-typed value that identifies the level of impersonation.


### -param pCallback [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iimpersonatecallback.md">IImpersonateCallback</a> interface whose method the framework calls for impersonation.


### -param pvCallbackContext [in, optional]

A pointer to a buffer that contains context information that is related to the impersonation call. The framework passes this context information in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a> method. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not have to supply a context. 


## -returns



<b>Impersonate</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



For information about how UMDF and UMDF drivers handle impersonation, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Impersonation</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554916">IImpersonateCallback::OnImpersonate</a>



<a href="..\wudfddi\nn-wudfddi-iimpersonatecallback.md">IImpersonateCallback</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::Impersonate method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

