---
UID: NF:wudfddi.IImpersonateCallback.OnImpersonate
title: IImpersonateCallback::OnImpersonate method
author: windows-driver-content
description: The OnImpersonate method handles impersonation.
old-location: wdf\iimpersonatecallback_onimpersonate.htm
old-project: wdf
ms.assetid: 6f06e89c-5298-4335-ab9a-ef69e635152c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IImpersonateCallback, IImpersonateCallback interface, OnImpersonate method, IImpersonateCallback::OnImpersonate, OnImpersonate method, OnImpersonate method, IImpersonateCallback interface, OnImpersonate,IImpersonateCallback.OnImpersonate, UMDFRequestObjectRef_e3752371-61b0-44ba-af86-0cf244e27894.xml, umdf.iimpersonatecallback_onimpersonate, wdf.iimpersonatecallback_onimpersonate, wudfddi/IImpersonateCallback::OnImpersonate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IImpersonateCallback.OnImpersonate
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IImpersonateCallback::OnImpersonate method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnImpersonate</b> method handles impersonation.


## -parameters




### -param Context [in, optional]

A pointer to a context that was previously supplied in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a> method. This parameter is optional and can be <b>NULL</b> if a context is not required. 


## -returns



None




## -remarks



Typically, the driver uses this callback to call a Win32 function directly. For example, if the driver must open a data file on behalf of an application that sent an I/O operation, the driver requires impersonation only to open the file handle.

To ensure that impersonation does not leak across driver callback functions or between device drivers, <b>OnImpersonate</b> should not call any framework methods.

A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554912">IImpersonateCallback</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a> method. 

For more information about how UMDF and UMDF drivers handle impersonation, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">Handling Impersonation</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554912">IImpersonateCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559136">IWDFIoRequest::Impersonate</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IImpersonateCallback::OnImpersonate method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

