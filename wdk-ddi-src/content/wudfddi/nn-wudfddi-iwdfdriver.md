---
UID: NN:wudfddi.IWDFDriver
title: IWDFDriver (wudfddi.h)
description: The IWDFDriver interface exposes the framework driver object that represents the driver image that is loaded in the host process.
old-location: wdf\iwdfdriver.htm
tech.root: wdf
ms.assetid: ada475ae-e697-475c-b461-8e3a36ae9ab1
ms.date: 02/26/2018
ms.keywords: IWDFDriver, IWDFDriver interface, IWDFDriver interface,described, UMDFDriverObjectRef_2bce205e-d670-4dae-870a-f5b01c3ea49e.xml, umdf.iwdfdriver, wdf.iwdfdriver, wudfddi/IWDFDriver
ms.topic: interface
f1_keywords:
 - "wudfddi/IWDFDriver"
req.header: wudfddi.h
req.include-header: 
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
- IWDFDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDriver interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFDriver</b> interface exposes the framework driver object that represents the driver image that is loaded in the host process.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFDriver</b> interface inherits from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFDriver</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFDriver</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">CreateDevice</a> method configures and creates a new framework device object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createpreallocatedwdfmemory">IWDFDriver::CreatePreallocatedWdfMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createpreallocatedwdfmemory">CreatePreallocatedWdfMemory</a> method creates a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-memory-object">framework memory object</a> for the specified buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createwdfmemory">IWDFDriver::CreateWdfMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createwdfmemory">CreateWdfMemory</a> method creates a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-memory-object">framework memory object</a> and allocates, for the memory object, a data buffer of the specified nonzero size.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createwdfobject">IWDFDriver::CreateWdfObject</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createwdfobject">CreateWdfObject</a> method creates a custom (or user) WDF object from a parent WDF object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-isversionavailable">IWDFDriver::IsVersionAvailable</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-isversionavailable">IsVersionAvailable</a> method determines whether the specified version of the framework is available.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-retrieveversionstring">IWDFDriver::RetrieveVersionString</a>
</td>
<td align="left" width="63%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-retrieveversionstring">RetrieveVersionString</a> method retrieves the version of the framework.

</td>
</tr>
</table> 

