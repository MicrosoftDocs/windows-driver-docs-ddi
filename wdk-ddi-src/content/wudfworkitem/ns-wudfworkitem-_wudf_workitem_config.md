---
UID: NS:wudfworkitem._WUDF_WORKITEM_CONFIG
title: "_WUDF_WORKITEM_CONFIG"
author: windows-driver-content
description: The WUDF_WORKITEM_CONFIG structure contains information that is associated with a work item.
old-location: wdf\wudf_workitem_config.htm
old-project: wdf
ms.assetid: 877C6641-30F9-44BC-9286-3B1D880482C9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWUDF_WORKITEM_CONFIG, PWUDF_WORKITEM_CONFIG, PWUDF_WORKITEM_CONFIG structure pointer, WUDF_WORKITEM_CONFIG, WUDF_WORKITEM_CONFIG structure, _WUDF_WORKITEM_CONFIG, umdf.wudf_workitem_config, wdf.wudf_workitem_config, wudfworkitem/PWUDF_WORKITEM_CONFIG, wudfworkitem/WUDF_WORKITEM_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfworkitem.h
req.include-header: 
req.target-type: Windows
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
-	WUDF_WORKITEM_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WUDF_WORKITEM_CONFIG, *PWUDF_WORKITEM_CONFIG
req.product: Windows 10 or later.
---

# _WUDF_WORKITEM_CONFIG structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The 
   
  <b>WUDF_WORKITEM_CONFIG</b> structure contains information that is associated with a work item.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field OnWorkItemFunc

The address of an <a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a> callback function.


### -field AutomaticSerialization

A Boolean value that, if TRUE, indicates that the framework will synchronize execution of the <a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a> callback function with callback functions from other objects that are underneath the work-item object's parent object. If FALSE, the framework does not synchronize execution of the <i>OnWorkItem</i> callback function.




## -remarks



Your driver must initialize the <b>WUDF_WORKITEM_CONFIG</b> structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh464097">WUDF_WORKITEM_CONFIG_INIT</a>. Your driver can then pass the structure to the <a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a> method as an input parameter.

Setting the <b>AutomaticSerialization</b> member of <b>WUDF_WORKITEM_CONFIG</b> to TRUE has no effect if the driver did not enable automatic callback synchronization by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff556991">IWDFDeviceInitialize::SetLockingConstraint</a>.




## -see-also




<a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>



<a href="https://msdn.microsoft.com/4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703">OnWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464097">WUDF_WORKITEM_CONFIG_INIT</a>
 

 

