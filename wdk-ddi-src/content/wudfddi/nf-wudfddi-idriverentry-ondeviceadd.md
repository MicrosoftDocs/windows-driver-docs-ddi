---
UID: NF:wudfddi.IDriverEntry.OnDeviceAdd
title: IDriverEntry::OnDeviceAdd method
author: windows-driver-content
description: The OnDeviceAdd method adds a new device to a system.
old-location: wdf\idriverentry_ondeviceadd.htm
old-project: wdf
ms.assetid: f2953b0d-6745-4804-bcda-47c7ddfb901f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDriverEntry, IDriverEntry interface, OnDeviceAdd method, IDriverEntry::OnDeviceAdd, OnDeviceAdd method, OnDeviceAdd method, IDriverEntry interface, OnDeviceAdd,IDriverEntry.OnDeviceAdd, UMDFDriverObjectRef_81d1022a-84b6-4a2e-a227-57f30c515171.xml, umdf.idriverentry_ondeviceadd, wdf.idriverentry_ondeviceadd, wudfddi/IDriverEntry::OnDeviceAdd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IDriverEntry.OnDeviceAdd
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IDriverEntry::OnDeviceAdd method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDeviceAdd</b> method adds a new device to a system.


## -syntax


````
HRESULT OnDeviceAdd(
  [in] IWDFDriver           *pWdfDriver,
  [in] IWDFDeviceInitialize *pWdfDeviceInit
);
````


## -parameters




### -param pWdfDriver [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> interface for the parent driver object that the new device belongs to.


### -param pWdfDeviceInit [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a> interface that the driver uses to initialize the newly created device.


## -returns



<b>OnDeviceAdd</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. The driver should return S_OK only if it successfully called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">framework device object</a>. If the driver returns an error code, UMDF tears down the entire device stack regardless of whether the driver is a filter driver or a function driver.




## -remarks



A new device object is created for each device that is loaded in the driver host process. When a new device arrives in the system, the framework calls <b>OnDeviceAdd</b> to notify the driver of the arrival and passes the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> and <a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a> interfaces in the call. The driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a> method to query for the device information that is provided as part of device installation. The driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to configure and create the device. If the driver does not successfully call <b>IWDFDriver::CreateDevice</b> before it returns S_OK, UMDF determines that the driver's behavior is incorrect and terminates the host process.

Any driver whose <b>OnDeviceAdd</b> method returns S_OK will subsequently receive a call to its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a> method when the UMDF tears down the device stack.

Do not use the <a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a> interface that the <i>pWdfDeviceInit</i> parameter points to after the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

For more information, see <a href="https://msdn.microsoft.com/233e3315-3044-42d7-867c-0a9e153eb53b">Adding a Device</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a>



<a href="..\wudfddi\nn-wudfddi-idriverentry.md">IDriverEntry</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IDriverEntry::OnDeviceAdd method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

