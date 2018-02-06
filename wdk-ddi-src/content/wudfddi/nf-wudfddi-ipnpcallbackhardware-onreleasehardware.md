---
UID: NF:wudfddi.IPnpCallbackHardware.OnReleaseHardware
title: IPnpCallbackHardware::OnReleaseHardware method
author: windows-driver-content
description: The OnReleaseHardware method notifies a driver to perform operations that are necessary when the specified hardware is no longer accessible.
old-location: wdf\ipnpcallbackhardware_onreleasehardware.htm
old-project: wdf
ms.assetid: 8975941a-21ad-4d51-9215-b35fa65cdfeb
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: OnReleaseHardware method, wudfddi/IPnpCallbackHardware::OnReleaseHardware, IPnpCallbackHardware, OnReleaseHardware method, IPnpCallbackHardware interface, OnReleaseHardware, IPnpCallbackHardware::OnReleaseHardware, wdf.ipnpcallbackhardware_onreleasehardware, umdf.ipnpcallbackhardware_onreleasehardware, UMDFDeviceObjectRef_d8966916-01c2-4e3d-b69b-d97ac06fe48a.xml, IPnpCallbackHardware interface, OnReleaseHardware method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IPnpCallbackHardware.OnReleaseHardware
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IPnpCallbackHardware::OnReleaseHardware method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnReleaseHardware</b> method notifies a driver to perform operations that are necessary when the specified hardware is no longer accessible.


## -syntax


````
HRESULT OnReleaseHardware(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface for the device object of the device that is no longer accessible.


## -returns


<b>OnReleaseHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).

This method must use the HRESULT_FROM_NT macro to return a specific HRESULT value to  return status to a kernel-mode client. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-kernel-mode-clients-in-umdf-1-x-drivers">Supporting Kernel-mode Clients</a>.



## -remarks


A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware.md">IPnpCallbackHardware</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object. 

The <b>OnReleaseHardware</b> method must free resources that were allocated during the call to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556766">IPnpCallbackHardware::OnPrepareHardware</a> method whether <b>OnPrepareHardware</b> succeeded or failed. Therefore, <b>OnReleaseHardware</b> must be able to handle the cleanup of partial resources.

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556766">IPnpCallbackHardware::OnPrepareHardware</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>

<a href="https://msdn.microsoft.com/652B92C2-EF04-482A-BB57-9F64F947EE4F">IPnpCallbackHardware2::OnReleaseHardware</a>

<a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware.md">IPnpCallbackHardware</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackHardware::OnReleaseHardware method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

