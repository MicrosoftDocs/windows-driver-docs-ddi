---
UID: NF:wudfworkitem.WUDF_WORKITEM_CONFIG_INIT
title: WUDF_WORKITEM_CONFIG_INIT function (wudfworkitem.h)
description: The WUDF_WORKITEM_CONFIG_INIT macro initializes a driver's WUDF_WORKITEM_CONFIG structure.
old-location: wdf\wudf_workitem_config_init.htm
tech.root: wdf
ms.assetid: A75AE18F-802F-462B-BF96-5C03408F53CA
ms.date: 02/26/2018
ms.keywords: WUDF_WORKITEM_CONFIG_INIT, WUDF_WORKITEM_CONFIG_INIT function, umdf.wudf_workitem_config_init, wdf.wudf_workitem_config_init, wudfworkitem/WUDF_WORKITEM_CONFIG_INIT
ms.topic: function
f1_keywords:
 - "wudfworkitem/WUDF_WORKITEM_CONFIG_INIT"
req.header: wudfworkitem.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wudfworkitem.h
api_name:
- WUDF_WORKITEM_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WUDF_WORKITEM_CONFIG_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The 
  <b>WUDF_WORKITEM_CONFIG_INIT</b> macro initializes a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a> structure.


## -parameters




### -param pConfig [out]

A pointer to the caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a> structure to initialize.


### -param OnWorkItemFunc [in]

The address of the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/nc-wudfworkitem-wudf_workitem_function">OnWorkItem</a> event callback function.


## -remarks



Drivers must call <b>WUDF_WORKITEM_CONFIG_INIT</b> before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createworkitem">IWDFDevice3::CreateWorkItem</a>.

The <b>WUDF_WORKITEM_CONFIG_INIT</b> function stores the pointer that the <i>OnWorkItemFunc</i> parameter specifies and sets the <b>AutomaticSerialization</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a> structure that is pointed to by the <i>pConfig</i> parameter to <b>TRUE</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-createworkitem">IWDFDevice3::CreateWorkItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfworkitem/ns-wudfworkitem-_wudf_workitem_config">WUDF_WORKITEM_CONFIG</a>
 

 

