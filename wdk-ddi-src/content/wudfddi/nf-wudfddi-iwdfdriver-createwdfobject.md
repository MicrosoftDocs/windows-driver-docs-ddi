---
UID: NF:wudfddi.IWDFDriver.CreateWdfObject
title: IWDFDriver::CreateWdfObject method
author: windows-driver-content
description: The CreateWdfObject method creates a custom (or user) WDF object from a parent WDF object.
old-location: wdf\iwdfdriver_createwdfobject.htm
old-project: wdf
ms.assetid: 9dda353d-7c39-4c3c-b9e2-38946d6cc086
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateWdfObject method, CreateWdfObject method, IWDFDriver interface, CreateWdfObject,IWDFDriver.CreateWdfObject, IWDFDriver, IWDFDriver interface, CreateWdfObject method, IWDFDriver::CreateWdfObject, UMDFDriverObjectRef_8ab61a3d-78e3-4d92-8a9c-0eff2837f65f.xml, umdf.iwdfdriver_createwdfobject, wdf.iwdfdriver_createwdfobject, wudfddi/IWDFDriver::CreateWdfObject
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
-	IWDFDriver.CreateWdfObject
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDriver::CreateWdfObject method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateWdfObject</b> method creates a custom (or user) WDF object from a parent WDF object.


## -parameters




### -param pCallbackInterface [in, optional]

A pointer to the <b>IUnknown</b> interface that the framework uses to determine the object-related event callback functions that the driver subscribes to on the newly created custom object. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification. If the driver passes a valid pointer, the framework will call <b>QueryInterface</b> on the <b>IUnknown</b> interface for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556754">IObjectCleanup</a> interface. If the framework obtains the driver's <b>IObjectCleanup</b> interface, the framework can subsequently call the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a> method to notify the driver that the custom object is cleaned up. 


### -param pParentObject [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a> interface for the parent WDF object. If <b>NULL</b>, the driver object becomes the default parent. 


### -param ppWdfObject [out]

A pointer to a buffer that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a> interface for the newly created WDF object.


## -returns



<b>CreateWdfObject</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The driver can call <b>CreateWdfObject</b> to create a general <a href="https://msdn.microsoft.com/9d400192-faf0-4d8f-849b-6b955105e21a">framework base object</a> for its own use. The driver can associate context memory, assign a parent object, and register an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556754">IObjectCleanup</a> interface. The framework subsequently calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a> method to clean up the child object. 

If no parent object is specified at the <i>pParentObject</i> parameter, the driver becomes the default parent. Therefore, when the driver object is deleted, the framework cleans up the child object. 

If a parent object is assigned, the child object is deleted when the parent object is deleted. In other words, the lifetime of a child object is scoped within that of the parent. 

If the driver must clean up the child object before the parent object is deleted, the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a> method. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556754">IObjectCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDriver::CreateWdfObject method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

