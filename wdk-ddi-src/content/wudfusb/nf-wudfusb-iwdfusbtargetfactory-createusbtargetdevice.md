---
UID: NF:wudfusb.IWDFUsbTargetFactory.CreateUsbTargetDevice
title: IWDFUsbTargetFactory::CreateUsbTargetDevice method
author: windows-driver-content
description: The CreateUsbTargetDevice method creates a USB device object that is also an I/O target.
old-location: wdf\iwdfusbtargetfactory_createusbtargetdevice.htm
old-project: wdf
ms.assetid: c5aeb5f4-be62-4418-981c-1dd4acdccf07
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateUsbTargetDevice method, CreateUsbTargetDevice method, IWDFUsbTargetFactory interface, CreateUsbTargetDevice,IWDFUsbTargetFactory.CreateUsbTargetDevice, IWDFUsbTargetFactory, IWDFUsbTargetFactory interface, CreateUsbTargetDevice method, IWDFUsbTargetFactory::CreateUsbTargetDevice, UMDFDeviceObjectRef_fafba7c5-57d5-4b05-bc46-46807b94ec6d.xml, umdf.iwdfusbtargetfactory_createusbtargetdevice, wdf.iwdfusbtargetfactory_createusbtargetdevice, wudfusb/IWDFUsbTargetFactory::CreateUsbTargetDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFUsbTargetFactory.CreateUsbTargetDevice
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# IWDFUsbTargetFactory::CreateUsbTargetDevice method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateUsbTargetDevice</b> method creates a USB device object that is also an I/O target.


## -syntax


````
HRESULT CreateUsbTargetDevice(
  [out] IWDFUsbTargetDevice **ppDevice
);
````


## -parameters




### -param ppDevice [out]

A pointer to a buffer that receives a pointer to the <a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a> interface for the USB target device object.


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

<a href="https://msdn.microsoft.com/c5aeb5f4-be62-4418-981c-1dd4acdccf07">CreateUsbTargetDevice</a> successfully created a USB device object that is also an I/O target. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY </b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/c5aeb5f4-be62-4418-981c-1dd4acdccf07">CreateUsbTargetDevice</a> encountered an allocation failure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>An error code that is defined in Winerror.h</b></dt>
</dl>
</td>
<td width="60%">
This value corresponds to the error code that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540277">WinUsb_Initialize</a> function returned.

</td>
</tr>
</table>
 




## -remarks



A UMDF driver should release the <a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a> interface pointer that the <b>CreateUsbTargetDevice</b> method returns in the <i>ppDevice</i> parameter when the driver is done with the interface.

If the file object that is associated with the created I/O target object is required, the driver should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559243">IWDFIoTarget::GetTargetFile</a> method. For more information about this file object, see <a href="https://msdn.microsoft.com/44bbc4c7-632d-4d75-94b9-f65e4d480e90">File Creation by a USB I/O Target</a>.

<div class="alert"><b>Note</b>  <b>CreateUsbTargetDevice</b> inherits all of the methods of the <a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a> interface.</div>
<div> </div>
To use the newly created USB I/O target object in a device stack, the INF file that installs the UMDF driver must contain the <b>UmdfDispatcher</b> directive and set <b>UmdfDispatcher</b> to <b>WinUsb</b> (<code>UmdfDispatcher=WinUsb</code>) in the <b>DDInstall.WDF</b> section. <b>UmdfDispatcher</b> is required to inform the UMDF platform that it can allow access to the USB I/O target. For more information about <b>UmdfDispatcher</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives</a>.


#### Examples

The following code example shows how to create and use a USB device object in an implementation of the UMDF driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556766">IPnpCallbackHardware::OnPrepareHardware</a> method.

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
    CComPtr&lt;IWDFUsbTargetFactory&gt; factory;
    USB_INTERFACE_DESCRIPTOR interfaceDescriptor;
    bool hidInterfaceFound = false;
    PUSB_HID_DESCRIPTOR hidDescriptor;
    NTSTATUS status;
    HRESULT hr = S_OK;
    //
    // Get the USB I/O target factory interface.
    //
    hr = WdfDevice-&gt;QueryInterface(IID_PPV_ARGS(&amp;factory));
    //
    // Create the USB I/O target.
    //
    hr = factory-&gt;CreateUsbTargetDevice(&amp;m_UsbTargetDevice);
    //
    // Get the configuration descriptor for the target device.
    //
    if (SUCCEEDED(hr))
    {
        hr = RetrieveConfigDescriptor(&amp;m_ConfigDescriptor, 
                                      &amp;m_ConfigDescriptorCb);
    }
    //
    // Iterate through the interfaces on the device and find the HID interface.
    //
    if (SUCCEEDED(hr))
    {
        CComPtr&lt;IWDFUsbInterface&gt; usbInterface;
        UCHAR index;
        bool found = true;
        for (index = 0; index &lt; m_ConfigDescriptor-&gt;bNumInterfaces; index += 1)
        {
            hr = m_UsbTargetDevice-&gt;RetrieveUsbInterface(index, &amp;usbInterface);
            if (SUCCEEDED(hr))
            {
                usbInterface-&gt;GetInterfaceDescriptor(&amp;interfaceDescriptor);
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
        if (SUCCEEDED(hr) &amp;&amp; (hidInterfaceFound == false))
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

<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetdevice.md">IWDFUsbTargetDevice</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a>



<a href="..\wudfusb\nn-wudfusb-iwdfusbtargetfactory.md">IWDFUsbTargetFactory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540277">WinUsb_Initialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559243">IWDFIoTarget::GetTargetFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFUsbTargetFactory::CreateUsbTargetDevice method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

