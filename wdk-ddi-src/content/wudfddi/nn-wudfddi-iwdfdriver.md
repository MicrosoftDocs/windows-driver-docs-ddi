---
UID: NN:wudfddi.IWDFDriver
title: IWDFDriver
author: windows-driver-content
description: The IWDFDriver interface exposes the framework driver object that represents the driver image that is loaded in the host process.
old-location: wdf\iwdfdriver.htm
tech.root: wdf
ms.assetid: ada475ae-e697-475c-b461-8e3a36ae9ab1
ms.date: 2/26/2018
ms.keywords: IWDFDriver, IWDFDriver interface, IWDFDriver interface,described, UMDFDriverObjectRef_2bce205e-d670-4dae-870a-f5b01c3ea49e.xml, umdf.iwdfdriver, wdf.iwdfdriver, wudfddi/IWDFDriver
ms.topic: interface
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDriver
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

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFDriver</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>. <b>IWDFDriver</b> also has these types of members:
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/df921271-b708-43bf-a250-048b7f638cac">CreateDevice</a> method configures and creates a new framework device object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558902">IWDFDriver::CreatePreallocatedWdfMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/9c24f42b-0f1d-4b93-99af-f4a5069b5223">CreatePreallocatedWdfMemory</a> method creates a <a href="https://msdn.microsoft.com/b5f7bb8b-115a-4536-9857-b7229ae2ec99">framework memory object</a> for the specified buffer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558905">IWDFDriver::CreateWdfMemory</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/2ea754db-3bed-48d9-825f-7ee7b5e169b7">CreateWdfMemory</a> method creates a <a href="https://msdn.microsoft.com/b5f7bb8b-115a-4536-9857-b7229ae2ec99">framework memory object</a> and allocates, for the memory object, a data buffer of the specified nonzero size.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558906">IWDFDriver::CreateWdfObject</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/9dda353d-7c39-4c3c-b9e2-38946d6cc086">CreateWdfObject</a> method creates a custom (or user) WDF object from a parent WDF object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558909">IWDFDriver::IsVersionAvailable</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/9048a568-3369-44eb-8fa8-361ce968a253">IsVersionAvailable</a> method determines whether the specified version of the framework is available.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558911">IWDFDriver::RetrieveVersionString</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/2fa320df-bafd-42f4-a0a1-14151c39d68a">RetrieveVersionString</a> method retrieves the version of the framework.

</td>
</tr>
</table> 

