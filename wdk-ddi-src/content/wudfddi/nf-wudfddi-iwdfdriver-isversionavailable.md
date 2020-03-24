---
UID: NF:wudfddi.IWDFDriver.IsVersionAvailable
title: IWDFDriver::IsVersionAvailable (wudfddi.h)
description: The IsVersionAvailable method determines whether the specified version of the framework is available.
old-location: wdf\iwdfdriver_isversionavailable.htm
tech.root: wdf
ms.assetid: 9048a568-3369-44eb-8fa8-361ce968a253
ms.date: 02/26/2018
keywords: ["IWDFDriver::IsVersionAvailable"]
ms.keywords: IWDFDriver interface,IsVersionAvailable method, IWDFDriver.IsVersionAvailable, IWDFDriver::IsVersionAvailable, IsVersionAvailable, IsVersionAvailable method, IsVersionAvailable method,IWDFDriver interface, UMDFDriverObjectRef_6ad78413-a8c5-4a9f-953d-94bd4eaf3425.xml, umdf.iwdfdriver_isversionavailable, wdf.iwdfdriver_isversionavailable, wudfddi/IWDFDriver::IsVersionAvailable
f1_keywords:
 - "wudfddi/IWDFDriver.IsVersionAvailable"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFDriver.IsVersionAvailable
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDriver::IsVersionAvailable


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IsVersionAvailable</b> method determines whether the specified version of the framework is available.


## -parameters




### -param pMinimumVersion [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-umdf_version_data">UMDF_VERSION_DATA</a> structure that describes the minimum version of the framework that the driver supports.


## -returns



<b>IsVersionAvailable</b> returns a BOOL value that indicates whether the given version of the framework is available. <b>TRUE</b> indicates the version of the framework is available. <b>FALSE</b> indicates the version of the framework is not available.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdriver">IWDFDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi_types/ns-wudfddi_types-umdf_version_data">UMDF_VERSION_DATA</a>
 

 

