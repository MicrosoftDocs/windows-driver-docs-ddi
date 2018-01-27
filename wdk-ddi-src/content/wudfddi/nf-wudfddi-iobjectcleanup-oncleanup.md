---
UID: NF:wudfddi.IObjectCleanup.OnCleanup
title: IObjectCleanup::OnCleanup method
author: windows-driver-content
description: The OnCleanup method releases any references to a WDF object to prevent interface leakage.
old-location: wdf\iobjectcleanup_oncleanup.htm
old-project: wdf
ms.assetid: 6b66c496-d1cc-4b7a-ae50-f18fffa7275a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: UMDFBaseObjectRef_1798eedf-b083-487c-b137-24d9caf1e7a7.xml, IObjectCleanup::OnCleanup, IObjectCleanup, OnCleanup method, OnCleanup method, IObjectCleanup interface, umdf.iobjectcleanup_oncleanup, wudfddi/IObjectCleanup::OnCleanup, OnCleanup, IObjectCleanup interface, OnCleanup method, wdf.iobjectcleanup_oncleanup
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
req.lib: wudfddi.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	Wudfddi.h
apiname: 
-	IObjectCleanup.OnCleanup
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IObjectCleanup::OnCleanup method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCleanup</b> method releases any references to a WDF object to prevent interface leakage.


## -syntax


````
void OnCleanup(
  [in] IWDFObject *pWdfObject
);
````


## -parameters




### -param pWdfObject [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a> interface of a object that is about to be released.


## -returns


None



## -remarks


The framework calls <b>OnCleanup</b> as part of a WDF object destruction sequence. The framework calls <b>OnCleanup</b> before the WDF object is destroyed.

A driver can register the <a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a> interface when the driver calls any of the following methods that creates a WDF object or that assigns a context to the WDF object: 
<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557021">IWDFDevice::CreateRequest</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558905">IWDFDriver::CreateWdfMemory</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558906">IWDFDriver::CreateWdfObject</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560208">IWDFObject::AssignContext</a>


</li>
</ul>


## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557021">IWDFDevice::CreateRequest</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558905">IWDFDriver::CreateWdfMemory</a>

<a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558906">IWDFDriver::CreateWdfObject</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560208">IWDFObject::AssignContext</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IObjectCleanup::OnCleanup method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

