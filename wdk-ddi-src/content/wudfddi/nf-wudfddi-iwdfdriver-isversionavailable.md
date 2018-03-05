---
UID: NF:wudfddi.IWDFDriver.IsVersionAvailable
title: IWDFDriver::IsVersionAvailable method
author: windows-driver-content
description: The IsVersionAvailable method determines whether the specified version of the framework is available.
old-location: wdf\iwdfdriver_isversionavailable.htm
old-project: wdf
ms.assetid: 9048a568-3369-44eb-8fa8-361ce968a253
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDriver, IWDFDriver interface, IsVersionAvailable method, IWDFDriver::IsVersionAvailable, IsVersionAvailable method, IsVersionAvailable method, IWDFDriver interface, IsVersionAvailable,IWDFDriver.IsVersionAvailable, UMDFDriverObjectRef_6ad78413-a8c5-4a9f-953d-94bd4eaf3425.xml, umdf.iwdfdriver_isversionavailable, wdf.iwdfdriver_isversionavailable, wudfddi/IWDFDriver::IsVersionAvailable
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
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
-	IWDFDriver.IsVersionAvailable
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDriver::IsVersionAvailable method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsVersionAvailable</b> method determines whether the specified version of the framework is available.


## -syntax


````
BOOL IsVersionAvailable(
  [in] UMDF_VERSION_DATA *pMinimumVersion
);
````


## -parameters




### -param pMinimumVersion [in]

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-umdf_version_data.md">UMDF_VERSION_DATA</a> structure that describes the minimum version of the framework that the driver supports.


## -returns



<b>IsVersionAvailable</b> returns a BOOL value that indicates whether the given version of the framework is available. <b>TRUE</b> indicates the version of the framework is available. <b>FALSE</b> indicates the version of the framework is not available.




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>



<a href="..\wudfddi_types\ns-wudfddi_types-umdf_version_data.md">UMDF_VERSION_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDriver::IsVersionAvailable method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

