---
UID: NF:wudfddi.IWDFDriver.CreateDevice
title: IWDFDriver::CreateDevice
author: windows-driver-content
description: The CreateDevice method configures and creates a new framework device object.
old-location: wdf\iwdfdriver_createdevice.htm
tech.root: wdf
ms.assetid: df921271-b708-43bf-a250-048b7f638cac
ms.date: 02/26/2018
ms.keywords: CreateDevice, CreateDevice method, CreateDevice method,IWDFDriver interface, IWDFDriver interface,CreateDevice method, IWDFDriver.CreateDevice, IWDFDriver::CreateDevice, UMDFDriverObjectRef_9afa4fd4-210b-4055-855a-1f922eb0fc9c.xml, umdf.iwdfdriver_createdevice, wdf.iwdfdriver_createdevice, wudfddi/IWDFDriver::CreateDevice
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
-	IWDFDriver.CreateDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDriver::CreateDevice


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateDevice</b> method configures and creates a new framework device object.


## -parameters




### -param pDeviceInit [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556965">IWDFDeviceInitialize</a> interface that represents the configuration properties for the new device to create.


### -param pCallbackInterface [in, optional]

A pointer to the <b>IUnknown</b> interface that the framework uses to obtain the interfaces that the driver provides for the new device object. These interfaces provide the callback functions that the framework calls when relevant events occur. For more information, see the following Remarks section.


### -param ppDevice [out]

A pointer to a buffer that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface for the new device object.


## -returns



<b>CreateDevice</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



The <b>IUnknown</b> interface that the driver supplies for the <i>pCallbackInterface</i> parameter can support several interfaces. The framework calls the <b>QueryInterface</b> method of the supplied <b>IUnknown</b> interface multiple times to retrieve the interfaces that the driver supports. The driver's <b>QueryInterface</b> method can return the following interfaces:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff554902">IFileCallbackCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554907">IFileCallbackClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556754">IObjectCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556762">IPnpCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556764">IPnpCallbackHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439727">IPnpCallbackHardware2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439744">IPnpCallbackHardwareInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556776">IPnpCallbackSelfManagedIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439744">IPnpCallbackHardwareInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556776">IPnpCallbackSelfManagedIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556815">IPowerPolicyCallbackWakeFromS0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556825">IPowerPolicyCallbackWakeFromSx</a>


When the device changes state, the framework calls the method that is related to the change (such as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> method) to notify the driver. 

If the call to <b>CreateDevice</b> is successful, the driver must eventually call the <b>IWDFDevice::Release</b> method. Note that the framework has its own reference count on the object.

For more information, see <a href="https://msdn.microsoft.com/233e3315-3044-42d7-867c-0a9e153eb53b">Adding a Device</a>.


#### Examples

The following code example shows an implementation of the <a href="https://msdn.microsoft.com/f2953b0d-6745-4804-bcda-47c7ddfb901f">OnDeviceAdd</a> method of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554885">IDriverEntry</a> interface. The framework calls <b>OnDeviceAdd</b> when a device is added to a computer.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT 
CDriver::OnDeviceAdd(
 IWDFDriver* pDriver,
 IWDFDeviceInitialize* pDeviceInit
    )
{
 IUnknown   *pDeviceCallback = NULL;
 IWDFDevice *pIWDFDevice     = NULL;
 IUnknown   *pIUnkQueue      = NULL;    

    //
    // Create the device callback object.
    //
    HRESULT hr = CDevice::CreateInstance(&amp;pDeviceCallback);

    //
    // Set device properties
    //
    if (S_OK == hr) {
        pDeviceInit-&gt;SetLockingConstraint(WdfDeviceLevel);
        // To register as the power-policy owner for 
        // the device stack, call the following:
        // pDeviceInit-&gt;SetPowerPolicyOwnership(TRUE);

        // For a filter driver, call the following:
        // pDeviceInit-&gt;SetFilter();
    }

    //
    // Request that the framework create a device object.
    // The device callback object is passed to inform the 
    // framework about the PnP callback functions the driver supports.
    //
    if (S_OK == hr) {
        hr = pDriver-&gt;CreateDevice(pDeviceInit, 
                                   pDeviceCallback,
                                   &amp;pIWDFDevice);
    }

    //
    // Create the queue callback object.
    //

    if (S_OK == hr) {
        hr = CQueue::CreateInstance(&amp;pIUnkQueue);
    }

    //
    // Configure the default queue. 
    // The queue callback object is passed to inform the 
    // framework about the queue callback functions the driver supports.
    //
    if (S_OK == hr) {
        IWDFIoQueue * pDefaultQueue = NULL;
        hr = pIWDFDevice-&gt;CreateIoQueue(
                       pIUnkQueue,
                       TRUE,                  // bDefaultQueue
                       WdfIoQueueDispatchParallel,
                       TRUE,                  // bPowerManaged
                       FALSE, //bAllowZeroLengthRequests
                       &amp;pDefaultQueue);
        SAFE_RELEASE(pDefaultQueue);
    }

    SAFE_RELEASE(pDeviceCallback);
    SAFE_RELEASE(pIWDFDevice);
    SAFE_RELEASE(pIUnkQueue);    

    return hr;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554902">IFileCallbackCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554907">IFileCallbackClose</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556754">IObjectCleanup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556762">IPnpCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556764">IPnpCallbackHardware</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556776">IPnpCallbackSelfManagedIo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556965">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a>
 

 

