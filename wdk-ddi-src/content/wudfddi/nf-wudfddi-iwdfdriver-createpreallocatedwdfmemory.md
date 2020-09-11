---
UID: NF:wudfddi.IWDFDriver.CreatePreallocatedWdfMemory
title: IWDFDriver::CreatePreallocatedWdfMemory (wudfddi.h)
description: The CreatePreallocatedWdfMemory method creates a framework memory object for the specified buffer.
old-location: wdf\iwdfdriver_createpreallocatedwdfmemory.htm
tech.root: wdf
ms.assetid: 9c24f42b-0f1d-4b93-99af-f4a5069b5223
ms.date: 02/26/2018
keywords: ["IWDFDriver::CreatePreallocatedWdfMemory"]
ms.keywords: CreatePreallocatedWdfMemory, CreatePreallocatedWdfMemory method, CreatePreallocatedWdfMemory method,IWDFDriver interface, IWDFDriver interface,CreatePreallocatedWdfMemory method, IWDFDriver.CreatePreallocatedWdfMemory, IWDFDriver::CreatePreallocatedWdfMemory, UMDFDriverObjectRef_273a5206-8415-4251-88e8-6f20c29f50e2.xml, umdf.iwdfdriver_createpreallocatedwdfmemory, wdf.iwdfdriver_createpreallocatedwdfmemory, wudfddi/IWDFDriver::CreatePreallocatedWdfMemory
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDriver::CreatePreallocatedWdfMemory
 - wudfddi/IWDFDriver::CreatePreallocatedWdfMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDriver.CreatePreallocatedWdfMemory
---

# IWDFDriver::CreatePreallocatedWdfMemory


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreatePreallocatedWdfMemory</b> method creates a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-memory-object">framework memory object</a> for the specified buffer.

## -parameters

### -param pBuff 

[in]
A pointer to a driver-supplied data buffer for the memory object.

### -param BufferSize 

[in]

      The size, in bytes, of data that <i>pBuff</i> points to.

### -param pCallbackInterface 

[in, optional]
A pointer to the <b>IUnknown</b> interface that the framework uses to determine the object-related event callback functions that the driver subscribes to on the newly created memory object. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification. The <b>IUnknown</b> interface is used for object cleanup and disposal. If the driver passes a valid pointer, the framework will call <b>QueryInterface</b> on the <b>IUnknown</b> interface for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a> interface. If the framework obtains the driver's <b>IObjectCleanup</b> interface, the framework can subsequently call the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a> method to notify the driver that the memory object is cleaned up.

### -param pParentObject 

[in, optional]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a> interface for the parent object of the created memory object. If <b>NULL</b>, the driver object becomes the default parent.

### -param ppWdfMemory 

[out]
A pointer to a buffer that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for the newly created WDF memory object.

## -returns

<b>CreatePreallocatedWdfMemory</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

The <b>CreatePreallocatedWdfMemory</b> method creates a framework memory object for a buffer that the driver previously allocated or obtained. 

A UMDF driver can call <b>CreatePreallocatedWdfMemory</b> if it must create a memory object that represents a pre-existing memory buffer. For example, the driver might receive a driver-defined structure within a buffer for an I/O request that contains an internal I/O control code. The driver can call <b>CreatePreallocatedWdfMemory</b> to create a memory object so that the driver can pass the structure to an I/O target. 

After a UMDF driver calls <b>CreatePreallocatedWdfMemory</b>, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfmemory-setbuffer">IWDFMemory::SetBuffer</a> to assign a different buffer to the memory object that <b>CreatePreallocatedWdfMemory</b> created. 

When the framework memory object that <b>CreatePreallocatedWdfMemory</b> created is deleted, the framework does not deallocate the pre-existing buffer. Likewise, a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfmemory-setbuffer">IWDFMemory::SetBuffer</a> does not deallocate the previously assigned buffer.


#### Examples

The following code example shows how to create a memory object for a buffer.


```
    //
    // Allocate a request.
    hr = wdfDevice->CreateRequest(NULL, NULL, &request);

    // Allocate a buffer and wrap it in a memory object. 
    // Make the memory object a child of the request. 
    // When the request object is deleted, the memory object 
    // is also deleted. 

    if (SUCCEEDED(hr))
    {
       buffer = new BYTE[m_HidDescriptor->wReportLength];

       if (buffer == NULL)
       {
          hr = E_OUTOFMEMORY;
       }
    }

    if (SUCCEEDED(hr))
    {
       CComPtr<IWDFDriver> driver;
       wdfDevice->GetDriver(&driver);

       hr = driver->CreatePreallocatedWdfMemory(
                       buffer,
                       m_HidDescriptor->wReportLength,
                       NULL,
                       request,
                       &memory
                       );
    }
```


## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdriver">IWDFDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfmemory-setbuffer">IWDFMemory::SetBuffer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>

