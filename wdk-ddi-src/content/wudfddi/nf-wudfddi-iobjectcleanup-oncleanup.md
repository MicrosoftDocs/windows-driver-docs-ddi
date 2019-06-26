---
UID: NF:wudfddi.IObjectCleanup.OnCleanup
title: IObjectCleanup::OnCleanup (wudfddi.h)
description: The OnCleanup method releases any references to a WDF object to prevent interface leakage.
old-location: wdf\iobjectcleanup_oncleanup.htm
tech.root: wdf
ms.assetid: 6b66c496-d1cc-4b7a-ae50-f18fffa7275a
ms.date: 02/26/2018
ms.keywords: IObjectCleanup interface,OnCleanup method, IObjectCleanup.OnCleanup, IObjectCleanup::OnCleanup, OnCleanup, OnCleanup method, OnCleanup method,IObjectCleanup interface, UMDFBaseObjectRef_1798eedf-b083-487c-b137-24d9caf1e7a7.xml, umdf.iobjectcleanup_oncleanup, wdf.iobjectcleanup_oncleanup, wudfddi/IObjectCleanup::OnCleanup
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IObjectCleanup.OnCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# IObjectCleanup::OnCleanup


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCleanup</b> method releases any references to a WDF object to prevent interface leakage.


## -parameters




### -param pWdfObject [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a> interface of a object that is about to be released.


## -returns



None




## -remarks



The framework calls <b>OnCleanup</b> as part of a WDF object destruction sequence. The framework calls <b>OnCleanup</b> before the WDF object is destroyed.

A driver can register the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a> interface when the driver calls any of the following methods that creates a WDF object or that assigns a context to the WDF object: 

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-createrequest">IWDFDevice::CreateRequest</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createpreallocatedwdfmemory">IWDFDriver::CreatePreallocatedWdfMemory</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createwdfmemory">IWDFDriver::CreateWdfMemory</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createwdfobject">IWDFDriver::CreateWdfObject</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfobject-assigncontext">IWDFObject::AssignContext</a>


</li>
</ul>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-createioqueue">IWDFDevice::CreateIoQueue</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdevice-createrequest">IWDFDevice::CreateRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createpreallocatedwdfmemory">IWDFDriver::CreatePreallocatedWdfMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createwdfmemory">IWDFDriver::CreateWdfMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfdriver-createwdfobject">IWDFDriver::CreateWdfObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-iwdfobject-assigncontext">IWDFObject::AssignContext</a>
 

 

