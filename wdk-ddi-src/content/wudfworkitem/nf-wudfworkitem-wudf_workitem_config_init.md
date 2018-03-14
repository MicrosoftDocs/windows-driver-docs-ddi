---
UID: NF:wudfworkitem.WUDF_WORKITEM_CONFIG_INIT
title: WUDF_WORKITEM_CONFIG_INIT function
author: windows-driver-content
description: The WUDF_WORKITEM_CONFIG_INIT macro initializes a driver's WUDF_WORKITEM_CONFIG structure.
old-location: wdf\wudf_workitem_config_init.htm
old-project: wdf
ms.assetid: A75AE18F-802F-462B-BF96-5C03408F53CA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WUDF_WORKITEM_CONFIG_INIT, WUDF_WORKITEM_CONFIG_INIT function, umdf.wudf_workitem_config_init, wdf.wudf_workitem_config_init, wudfworkitem/WUDF_WORKITEM_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wudfworkitem.h
api_name:
-	WUDF_WORKITEM_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: UNICODE_STRING
req.product: Windows 10 or later.
---

# WUDF_WORKITEM_CONFIG_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The 
  <b>WUDF_WORKITEM_CONFIG_INIT</b> macro initializes a driver's <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure.


## -syntax


````
void WUDF_WORKITEM_CONFIG_INIT(
  _Out_ PWUDF_WORKITEM_CONFIG pConfig,
  _In_  PFN_WUDF_WORKITEM     OnWorkItemFunc
);
````


## -parameters




### -param pConfig [out]

A pointer to the caller-allocated <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure to initialize.


### -param OnWorkItemFunc [in]

The address of the driver's <a href="..\wudfworkitem\nc-wudfworkitem-wudf_workitem_function.md">OnWorkItem</a> event callback function.


## -returns



This function does not return a value.




## -remarks



Drivers must call <b>WUDF_WORKITEM_CONFIG_INIT</b> before calling <a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>.

The <b>WUDF_WORKITEM_CONFIG_INIT</b> function stores the pointer that the <i>OnWorkItemFunc</i> parameter specifies and sets the <b>AutomaticSerialization</b> member of the <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure that is pointed to by the <i>pConfig</i> parameter to <b>TRUE</b>.




## -see-also

<a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a>



<a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>



 

 


