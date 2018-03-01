---
UID: NF:wudfddi.IWDFObject.ReleaseLock
title: IWDFObject::ReleaseLock method
author: windows-driver-content
description: The ReleaseLock method allows the framework to call methods of interfaces that are registered by the driver that the framework previously prevented from calling because the driver called the IWDFObject::AcquireLock method.
old-location: wdf\iwdfobject_releaselock.htm
old-project: wdf
ms.assetid: 05771d81-d2e1-4787-a190-e7ef4d9ebcc9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFObject, IWDFObject interface, ReleaseLock method, IWDFObject::ReleaseLock, ReleaseLock method, ReleaseLock method, IWDFObject interface, ReleaseLock,IWDFObject.ReleaseLock, UMDFBaseObjectRef_bdc7490f-170b-42bb-91af-435ee5dc3e5a.xml, umdf.iwdfobject_releaselock, wdf.iwdfobject_releaselock, wudfddi/IWDFObject::ReleaseLock
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
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFObject::ReleaseLock method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ReleaseLock</b> method allows the framework to call methods of interfaces that are registered by the driver that the framework previously prevented from calling because the driver called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560204">IWDFObject::AcquireLock</a> method.


## -syntax


````
void ReleaseLock();
````


## -parameters






## -returns



None




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560204">IWDFObject::AcquireLock</a>



<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFObject::ReleaseLock method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

