---
UID: NF:wudfddi.IWDFDriver.CreateWdfMemory
title: IWDFDriver::CreateWdfMemory method
author: windows-driver-content
description: The CreateWdfMemory method creates a framework memory object and allocates, for the memory object, a data buffer of the specified nonzero size.
old-location: wdf\iwdfdriver_createwdfmemory.htm
old-project: wdf
ms.assetid: 2ea754db-3bed-48d9-825f-7ee7b5e169b7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: CreateWdfMemory method, IWDFDriver::CreateWdfMemory, IWDFDriver, CreateWdfMemory method, IWDFDriver interface, wdf.iwdfdriver_createwdfmemory, UMDFDriverObjectRef_903775e8-0752-435b-96d9-fa1317f63289.xml, CreateWdfMemory, wudfddi/IWDFDriver::CreateWdfMemory, umdf.iwdfdriver_createwdfmemory, IWDFDriver interface, CreateWdfMemory method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDriver.CreateWdfMemory
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDriver::CreateWdfMemory method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateWdfMemory</b> method creates a <a href="https://msdn.microsoft.com/b5f7bb8b-115a-4536-9857-b7229ae2ec99">framework memory object</a> and allocates, for the memory object, a data buffer of the specified nonzero size.


## -syntax


````
HRESULT CreateWdfMemory(
  [in]           SIZE_T     BufferSize,
  [in, optional] IUnknown   *pCallbackInterface,
  [in, optional] IWDFObject *pParentObject,
  [out]          IWDFMemory **ppWdfMemory
);
````


## -parameters




### -param BufferSize [in]


            The nonzero specified size, in bytes, of data for the newly created WDF memory object's data buffer. 
          


### -param pCallbackInterface [in, optional]

A pointer to the <b>IUnknown</b> interface that the framework uses to determine the object-related event callback functions that the driver subscribes to on the newly created memory object. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification. The <b>IUnknown</b> interface is used for object cleanup and disposal. If the driver passes a valid pointer, the framework will call <b>QueryInterface</b> on the <b>IUnknown</b> interface for the <a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a> interface. If the framework obtains the driver's <b>IObjectCleanup</b> interface, the framework can subsequently call the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a> method to notify the driver that the memory object is cleaned up. 


### -param pParentObject [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a> interface for the parent object of the created memory object. If <b>NULL</b>, the driver object becomes the default parent. 


### -param ppWdfMemory [out]

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface for the newly created WDF memory object.


## -returns


<b>CreateWdfMemory</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.



## -remarks


The <b>CreateWdfMemory</b> method allocates a buffer of the size that the <i>BufferSize</i> parameter specifies, and creates a framework memory object that represents the buffer. 

If <b>NULL</b> is specified in the <i>pParentObject</i> parameter, the driver object becomes the default parent object for the newly created memory object. If a UMDF driver creates a memory object that the driver uses with a specific device object, request object, or other framework object, the driver should set the memory object's parent object appropriately. When the parent object is deleted, the memory object and its buffer are deleted. 

A UMDF driver can also delete a memory object and its buffer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a>. 

A UMDF driver cannot create a memory object with a zero-specified size buffer. If a driver must use a zero-specified size buffer, the driver should use a <b>NULL</b> memory object instead. For example, if the driver must use a zero-specified size buffer in a read request, the driver must pass <b>NULL</b> to the <i>pOutputMemory</i> parameter in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a> method.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>

<a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a>

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559233">IWDFIoTarget::FormatRequestForRead</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDriver::CreateWdfMemory method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

