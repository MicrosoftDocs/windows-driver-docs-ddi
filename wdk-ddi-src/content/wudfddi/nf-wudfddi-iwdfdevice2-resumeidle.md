---
UID: NF:wudfddi.IWDFDevice2.ResumeIdle
title: IWDFDevice2::ResumeIdle method
author: windows-driver-content
description: The ResumeIdle method informs the framework that the device is not in use and can be placed in a device low-power state if it remains idle.
old-location: wdf\iwdfdevice2_resumeidle.htm
old-project: wdf
ms.assetid: e821f738-3712-49c2-9026-ff6ddc0381a6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: umdf.iwdfdevice2_resumeidle, ResumeIdle method, IWDFDevice2 interface, wudfddi/IWDFDevice2::ResumeIdle, IWDFDevice2::ResumeIdle, ResumeIdle, wdf.iwdfdevice2_resumeidle, IWDFDevice2 interface, ResumeIdle method, IWDFDevice2, ResumeIdle method, UMDFDeviceObjectRef_2c3c90d0-ac7d-44ac-b643-7dd6abd8ac67.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	IWDFDevice2.ResumeIdle
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDevice2::ResumeIdle method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ResumeIdle</b> method informs the framework that the device is not in use and can be placed in a device low-power state if it remains idle.


## -syntax


````
void ResumeIdle();
````


## -parameters





## -returns


None.



## -remarks


Every call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556948">IWDFDevice2::StopIdle</a> must eventually be followed by a call to <b>ResumeIdle</b>, or else the device will never return to a low-power state if it again becomes idle.

For more information about <a href="https://msdn.microsoft.com/1a4907c9-8e3b-4fb6-a7d4-89985e470e48">StopIdle</a> and <b>ResumeIdle</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556948">IWDFDevice2::StopIdle</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::ResumeIdle method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

