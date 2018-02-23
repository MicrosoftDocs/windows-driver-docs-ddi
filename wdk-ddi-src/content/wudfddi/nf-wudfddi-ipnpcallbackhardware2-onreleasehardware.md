---
UID: NF:wudfddi.IPnpCallbackHardware2.OnReleaseHardware
title: IPnpCallbackHardware2::OnReleaseHardware method
author: windows-driver-content
description: The OnReleaseHardware method performs operations that are needed when a device is no longer accessible.
old-location: wdf\ipnpcallbackhardware2_onreleasehardware.htm
old-project: wdf
ms.assetid: 652B92C2-EF04-482A-BB57-9F64F947EE4F
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wudfddi/IPnpCallbackHardware2::OnReleaseHardware, OnReleaseHardware, umdf.ipnpcallbackhardware2_onreleasehardware, IPnpCallbackHardware2 interface, OnReleaseHardware method, IPnpCallbackHardware2::OnReleaseHardware, OnReleaseHardware method, IPnpCallbackHardware2 interface, OnReleaseHardware method, wdf.ipnpcallbackhardware2_onreleasehardware, IPnpCallbackHardware2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	IPnpCallbackHardware2.OnReleaseHardware
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPnpCallbackHardware2::OnReleaseHardware method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnReleaseHardware</b> method performs operations that are needed when a device is no longer accessible.


## -syntax


````
HRESULT OnReleaseHardware(
  [in] IWDFDevice3        *pWdfDevice,
  [in] IWDFCmResourceList *pWdfResourcesTranslated
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface for the framework device object.


### -param pWdfResourcesTranslated [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfcmresourcelist.md">IWDFCmResourceList</a> interface for the framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns



<b>OnReleaseHardware</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. Do not return HRESULT_FROM_NT(STATUS_NOT_SUPPORTED).




## -remarks



A driver registers the <a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware2.md">IPnpCallbackHardware2</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create a device object.

 
The <b>OnReleaseHardware</b> method must free resources that were allocated during the call to the driver's <a href="https://msdn.microsoft.com/830D706A-016C-4637-829F-2014AD1A1309">IPnpCallbackHardware2::OnPrepareHardware</a> method, regardless of whether <b>OnPrepareHardware</b> succeeded or failed. As such, <b>OnReleaseHardware</b> must be able to handle the cleanup of partial resources.

For information about deleting an interrupt object, see <a href="https://msdn.microsoft.com/B72DA452-B22F-47CD-8C5D-E741F09F556E">Deleting an Interrupt Object</a>.

For information about parsing hardware resources, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.



#### Examples

See example code in <a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a>



<a href="..\wudfddi\nn-wudfddi-ipnpcallbackhardware2.md">IPnpCallbackHardware2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackHardware2::OnReleaseHardware method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

