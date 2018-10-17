---
UID: NF:wudfddi.IWDFDevice.GetDriver
title: IWDFDevice::GetDriver
author: windows-driver-content
description: The GetDriver method retrieves the interface to the parent driver object of a device instance.
old-location: wdf\iwdfdevice_getdriver.htm
tech.root: wdf
ms.assetid: 5d17d970-56b7-494a-aa7b-d60065ff06d8
ms.date: 2/26/2018
ms.keywords: GetDriver, GetDriver method, GetDriver method,IWDFDevice interface, IWDFDevice interface,GetDriver method, IWDFDevice.GetDriver, IWDFDevice::GetDriver, UMDFDeviceObjectRef_6c0cfbb6-1ee7-4c7b-b4ec-0b957630e094.xml, umdf.iwdfdevice_getdriver, wdf.iwdfdevice_getdriver, wudfddi/IWDFDevice::GetDriver
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
-	IWDFDevice.GetDriver
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDevice::GetDriver


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetDriver</b> method retrieves the interface to the parent driver object of a device instance.


## -parameters




### -param ppWdfDriver [out]

A pointer to a variable that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a> interface for the parent driver object.


## -returns



None




## -remarks



For a code example of how to use the GetDriver method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558905">IWDFDriver::CreateWdfMemory</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a>
 

 

