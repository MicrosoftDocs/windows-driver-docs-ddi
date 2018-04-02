---
UID: NF:wudfddi.IWDFObject.DeleteWdfObject
title: IWDFObject::DeleteWdfObject method
author: windows-driver-content
description: The DeleteWdfObject method deletes a previously created Microsoft Windows Driver Frameworks (WDF) object.
old-location: wdf\iwdfobject_deletewdfobject.htm
old-project: wdf
ms.assetid: a777b8df-e255-402a-aa55-14e5861b215f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DeleteWdfObject method, DeleteWdfObject method, IWDFObject interface, DeleteWdfObject,IWDFObject.DeleteWdfObject, IWDFObject, IWDFObject interface, DeleteWdfObject method, IWDFObject::DeleteWdfObject, UMDFBaseObjectRef_e8c4d75a-eed6-4da3-9cce-79d863a01cd6.xml, umdf.iwdfobject_deletewdfobject, wdf.iwdfobject_deletewdfobject, wudfddi/IWDFObject::DeleteWdfObject
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
-	IWDFObject.DeleteWdfObject
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFObject::DeleteWdfObject method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>DeleteWdfObject</b> method deletes a previously created Microsoft Windows Driver Frameworks (WDF) object.


## -parameters






## -returns



<b>DeleteWdfObject</b> returns S_OK if the operation succeeds. Otherwise, this method returns HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED) or one of the other error codes that are defined in Winerror.h. 




## -remarks



A driver is unable to delete some WDF objects. For example, the driver cannot delete a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">framework device object</a> because the framework owns and controls device objects. For more information about the hierarchy of WDF objects, see <a href="https://msdn.microsoft.com/ffacca8f-4083-4998-83d2-7c31544eb497">Framework Object Hierarchy</a>. 

The driver typically deletes only WDF objects that it creates and owns. For more information about deleting framework objects, see <a href="https://msdn.microsoft.com/55ad8133-a70a-462f-87cd-6aeaffb0aec8">Managing the Lifetime of Objects</a>. 

However, when a parent object is deleted, all child objects are automatically deleted. For example, if the driver called <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> to create an I/O queue object, the newly created I/O queue becomes a child of the device object. The I/O queue object is then automatically deleted when the device object is deleted without the driver explicitly calling <b>DeleteWdfObject</b>.


#### Examples

For a code example of how to use the <b>DeleteWdfObject</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558892">IWDFDevice::SetPnpState</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>
 

 

