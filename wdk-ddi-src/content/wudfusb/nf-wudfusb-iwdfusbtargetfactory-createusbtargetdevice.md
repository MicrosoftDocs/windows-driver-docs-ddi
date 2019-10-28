---
UID: NF:wudfusb.IWDFUsbTargetFactory.CreateUsbTargetDevice
title: IWDFUsbTargetFactory::CreateUsbTargetDevice (wudfusb.h)
description: The CreateUsbTargetDevice method creates a USB device object that is also an I/O target.
old-location: wdf\iwdfusbtargetfactory_createusbtargetdevice.htm
tech.root: wdf
ms.assetid: c5aeb5f4-be62-4418-981c-1dd4acdccf07
ms.date: 02/26/2018
ms.keywords: CreateUsbTargetDevice, CreateUsbTargetDevice method, CreateUsbTargetDevice method,IWDFUsbTargetFactory interface, IWDFUsbTargetFactory interface,CreateUsbTargetDevice method, IWDFUsbTargetFactory.CreateUsbTargetDevice, IWDFUsbTargetFactory::CreateUsbTargetDevice, UMDFDeviceObjectRef_fafba7c5-57d5-4b05-bc46-46807b94ec6d.xml, umdf.iwdfusbtargetfactory_createusbtargetdevice, wdf.iwdfusbtargetfactory_createusbtargetdevice, wudfusb/IWDFUsbTargetFactory::CreateUsbTargetDevice
ms.topic: method
f1_keywords:
 - "wudfusb/IWDFUsbTargetFactory.CreateUsbTargetDevice"
req.header: wudfusb.h
req.include-header: Wudfusb.h
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
- IWDFUsbTargetFactory.CreateUsbTargetDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFUsbTargetFactory::CreateUsbTargetDevice


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateUsbTargetDevice</b> method creates a USB device object that is also an I/O target.


## -parameters




### -param ppDevice [out]

A pointer to a buffer that receives a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetdevice">IWDFUsbTargetDevice</a> interface for the USB target device object.


## -returns



<b>CreateUsbTargetDevice</b> returns one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetfactory-createusbtargetdevice">CreateUsbTargetDevice</a> successfully created a USB device object that is also an I/O target. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nf-wudfusb-iwdfusbtargetfactory-createusbtargetdevice">CreateUsbTargetDevice</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the <a href="https://docs.microsoft.com/windows/desktop/api/winusb/nf-winusb-winusb_initialize">WinUsb_Initialize</a> function returned.

</td>
</tr>
</table>
 




## -remarks



A UMDF driver should release the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetdevice">IWDFUsbTargetDevice</a> interface pointer that the <b>CreateUsbTargetDevice</b> method returns in the <i>ppDevice</i> parameter when the driver is done with the interface.

If the file object that is associated with the created I/O target object is required, the driver should call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-gettargetfile">IWDFIoTarget::GetTargetFile</a> method. For more information about this file object, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/file-creation-by-a-usb-i-o-target">File Creation by a USB I/O Target</a>.

<div class="alert"><b>Note</b>  <b>CreateUsbTargetDevice</b> inherits all of the methods of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a> interface.</div>
<div> </div>
To use the newly created USB I/O target object in a device stack, the INF file that installs the UMDF driver must contain the <b>UmdfDispatcher</b> directive and set <b>UmdfDispatcher</b> to <b>WinUsb</b> (<code>UmdfDispatcher=WinUsb</code>) in the <b>DDInstall.WDF</b> section. <b>UmdfDispatcher</b> is required to inform the UMDF platform that it can allow access to the USB I/O target. For more information about <b>UmdfDispatcher</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives</a>.


#### Examples

The following code example shows how to create and use a USB device object in an implementation of the UMDF driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallbackhardware-onpreparehardware">IPnpCallbackHardware::OnPrepareHardware</a> method.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT
CUmdfHidDevice::OnPrepareHardware(
    __in IWDFDevice* WdfDevice
    )
{
    CComPtr<IWDFUsbTargetFactory> factory;
    USB_INTERFACE_DESCRIPTOR interfaceDescriptor;
    bool hidInterfaceFound = false;
    PUSB_HID_DESCRIPTOR hidDescriptor;
    NTSTATUS status;
    HRESULT hr = S_OK;
    //
    // Get the USB I/O target factory interface.
    //
    hr = WdfDevice->QueryInterface(IID_PPV_ARGS(&factory));
    //
    // Create the USB I/O target.
    //
    hr = factory->CreateUsbTargetDevice(&m_UsbTargetDevice);
    //
    // Get the configuration descriptor for the target device.
    //
    if (SUCCEEDED(hr))
    {
        hr = RetrieveConfigDescriptor(&m_ConfigDescriptor, 
                                      &m_ConfigDescriptorCb);
    }
    //
    // Iterate through the interfaces on the device and find the HID interface.
    //
    if (SUCCEEDED(hr))
    {
        CComPtr<IWDFUsbInterface> usbInterface;
        UCHAR index;
        bool found = true;
        for (index = 0; index < m_ConfigDescriptor->bNumInterfaces; index += 1)
        {
            hr = m_UsbTargetDevice->RetrieveUsbInterface(index, &usbInterface);
            if (SUCCEEDED(hr))
            {
                usbInterface->GetInterfaceDescriptor(&interfaceDescriptor);
                if (interfaceDescriptor.bInterfaceClass == 0x3)
                {
                    hidInterfaceFound = true;
                    break;
                }
            }
            else
            {
                break;
            }
        }
        if (SUCCEEDED(hr) && (hidInterfaceFound == false))
        {
            hr = E_FAIL;
        }
    }
    //
    // Get the HID descriptor associated with this interface.
    //
    if (SUCCEEDED(hr))
    {
        hr = ParseHidDescriptor(
                                m_ConfigDescriptor,
                                m_ConfigDescriptorCb,
                                interfaceDescriptor.bInterfaceNumber
                                );
    }
    //
    // Process the HID information from the device and setup 
    // the collection data structures.
    //
    if (SUCCEEDED(hr))
    {
        hr = SetupCollections();
    }
    return hr;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-gettargetfile">IWDFIoTarget::GetTargetFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetdevice">IWDFUsbTargetDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfusb/nn-wudfusb-iwdfusbtargetfactory">IWDFUsbTargetFactory</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winusb/nf-winusb-winusb_initialize">WinUsb_Initialize</a>
 

 

