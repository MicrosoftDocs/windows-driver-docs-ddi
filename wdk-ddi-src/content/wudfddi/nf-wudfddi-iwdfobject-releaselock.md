---
UID: NF:wudfddi.IWDFObject.ReleaseLock
title: IWDFObject::ReleaseLock
author: windows-driver-content
description: The ReleaseLock method allows the framework to call methods of interfaces that are registered by the driver that the framework previously prevented from calling because the driver called the IWDFObject::AcquireLock method.
old-location: wdf\iwdfobject_releaselock.htm
old-project: wdf
ms.assetid: 05771d81-d2e1-4787-a190-e7ef4d9ebcc9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFObject interface,ReleaseLock method, IWDFObject.ReleaseLock, IWDFObject::ReleaseLock, ReleaseLock, ReleaseLock method, ReleaseLock method,IWDFObject interface, UMDFBaseObjectRef_bdc7490f-170b-42bb-91af-435ee5dc3e5a.xml, umdf.iwdfobject_releaselock, wdf.iwdfobject_releaselock, wudfddi/IWDFObject::ReleaseLock
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
-	IWDFObject.ReleaseLock
product: Windows
targetos: Windows
req.typenames: 
---

# IWDFObject::ReleaseLock


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ReleaseLock</b> method allows the framework to call methods of interfaces that are registered by the driver that the framework previously prevented from calling because the driver called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560204">IWDFObject::AcquireLock</a> method.


## -parameters






## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560204">IWDFObject::AcquireLock</a>
 

 

