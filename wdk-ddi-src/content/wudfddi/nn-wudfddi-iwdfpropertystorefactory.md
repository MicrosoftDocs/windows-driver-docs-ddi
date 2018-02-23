---
UID: NN:wudfddi.IWDFPropertyStoreFactory
title: IWDFPropertyStoreFactory
author: windows-driver-content
description: The IWDFPropertyStoreFactory interface is a factory interface that is used to create a property store interface.
old-location: wdf\iwdfpropertystorefactory.htm
old-project: wdf
ms.assetid: 41d77cf1-6f85-4f43-b2d8-1da4c9dac380
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.iwdfpropertystorefactory, IWDFPropertyStoreFactory interface, IWDFPropertyStoreFactory interface, described, IWDFPropertyStoreFactory, wudfddi/IWDFPropertyStoreFactory, UMDFDeviceObjectRef_07ada2e1-57a4-4b48-9145-fd38baef01cf.xml, umdf.iwdfpropertystorefactory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	IWDFPropertyStoreFactory
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFPropertyStoreFactory interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFPropertyStoreFactory</b> interface is a factory interface that is used to create a property store interface.


## -members

The <b>IWDFPropertyStoreFactory</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a property store interface that drivers can use to access the registry.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a property store interface that drivers can use to access the registry.

 


## -remarks



Drivers obtain the <b>IWDFPropertyStoreFactory</b> interface by calling <b>IWDFDevice::QueryInterface</b>,  <b>IWDFDeviceInitialize::QueryInterface</b> or <b>IWDFDeviceInitialize2::QueryInterface</b>.



