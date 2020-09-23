---
UID: NF:wudfddi.IWDFDriver.CreateWdfMemory
title: IWDFDriver::CreateWdfMemory (wudfddi.h)
description: The CreateWdfMemory method creates a framework memory object and allocates, for the memory object, a data buffer of the specified nonzero size.
old-location: wdf\iwdfdriver_createwdfmemory.htm
tech.root: wdf
ms.assetid: 2ea754db-3bed-48d9-825f-7ee7b5e169b7
ms.date: 02/26/2018
keywords: ["IWDFDriver::CreateWdfMemory"]
ms.keywords: CreateWdfMemory, CreateWdfMemory method, CreateWdfMemory method,IWDFDriver interface, IWDFDriver interface,CreateWdfMemory method, IWDFDriver.CreateWdfMemory, IWDFDriver::CreateWdfMemory, UMDFDriverObjectRef_903775e8-0752-435b-96d9-fa1317f63289.xml, umdf.iwdfdriver_createwdfmemory, wdf.iwdfdriver_createwdfmemory, wudfddi/IWDFDriver::CreateWdfMemory
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
 - IWDFDriver::CreateWdfMemory
 - wudfddi/IWDFDriver::CreateWdfMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDriver.CreateWdfMemory
---

# IWDFDriver::CreateWdfMemory


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateWdfMemory</b> method creates a <a href="/windows-hardware/drivers/wdf/framework-memory-object">framework memory object</a> and allocates, for the memory object, a data buffer of the specified nonzero size.

## -parameters

### -param BufferSize 

[in]

The nonzero specified size, in bytes, of data for the newly created WDF memory object's data buffer.

### -param pCallbackInterface 

[in, optional]
A pointer to the <b>IUnknown</b> interface that the framework uses to determine the object-related event callback functions that the driver subscribes to on the newly created memory object. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification. The <b>IUnknown</b> interface is used for object cleanup and disposal. If the driver passes a valid pointer, the framework will call <b>QueryInterface</b> on the <b>IUnknown</b> interface for the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a> interface. If the framework obtains the driver's <b>IObjectCleanup</b> interface, the framework can subsequently call the driver's <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a> method to notify the driver that the memory object is cleaned up.

### -param pParentObject 

[in, optional]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a> interface for the parent object of the created memory object. If <b>NULL</b>, the driver object becomes the default parent.

### -param ppWdfMemory 

[out]
A pointer to a buffer that receives a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface for the newly created WDF memory object.

## -returns

<b>CreateWdfMemory</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

The <b>CreateWdfMemory</b> method allocates a buffer of the size that the <i>BufferSize</i> parameter specifies, and creates a framework memory object that represents the buffer. 

If <b>NULL</b> is specified in the <i>pParentObject</i> parameter, the driver object becomes the default parent object for the newly created memory object. If a UMDF driver creates a memory object that the driver uses with a specific device object, request object, or other framework object, the driver should set the memory object's parent object appropriately. When the parent object is deleted, the memory object and its buffer are deleted. 

A UMDF driver can also delete a memory object and its buffer by calling <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a>. 

A UMDF driver cannot create a memory object with a zero-specified size buffer. If a driver must use a zero-specified size buffer, the driver should use a <b>NULL</b> memory object instead. For example, if the driver must use a zero-specified size buffer in a read request, the driver must pass <b>NULL</b> to the <i>pOutputMemory</i> parameter in a call to the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforread">IWDFIoTarget::FormatRequestForRead</a> method.


#### Examples

The following code example shows how to create a memory object that can hold information that is read from a USB endpoint.


```
HRESULT
CUmdfHidDevice::PrepareReader(
    VOID
    )
{
    CComPtr<IWDFDevice> wdfDevice;
    CComPtr<IWDFDriver> wdfDriver;
    CComPtr<IWDFIoRequest> wdfRequest;

    HRESULT hr;

    GetWdfDevice(&wdfDevice);
    wdfDevice->GetDriver(&wdfDriver);

    // Open the interrupt pipe.
    hr = m_HidInterface->RetrieveUsbPipeObject(
                         USB_HID_INTERRUPT_PIPE_INDEX,
                         &m_InterruptPipe
                         );

    // Allocate a memory object to hold information that 
    // is read from the interrupt pipe. 
    // This memory object will be reused.
    if (SUCCEEDED(hr))
    {
        hr = wdfDriver->CreateWdfMemory(m_ReadBufferSize,
                                        NULL,
                                        wdfDevice,
                                        &m_ReadMemory);
    }

    return hr;
}
```


## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdriver">IWDFDriver</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforread">IWDFIoTarget::FormatRequestForRead</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-deletewdfobject">IWDFObject::DeleteWdfObject</a>