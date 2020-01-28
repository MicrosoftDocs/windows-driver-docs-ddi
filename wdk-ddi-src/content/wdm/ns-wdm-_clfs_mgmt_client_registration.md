---
UID: NS:wdm._CLFS_MGMT_CLIENT_REGISTRATION
title: _CLFS_MGMT_CLIENT_REGISTRATION (wdm.h)
description: The CLFS_MGMT_CLIENT_REGISTRATION structure is given to CLFS management by clients who manage their own logs.
old-location: kernel\clfs_mgmt_client_registration.htm
tech.root: kernel
ms.assetid: 4f4f7ece-efe4-49f7-a6ce-bc131d1c1968
ms.date: 04/30/2018
ms.keywords: "*PCLFS_MGMT_CLIENT_REGISTRATION, CLFS_MGMT_CLIENT_REGISTRATION, CLFS_MGMT_CLIENT_REGISTRATION structure [Kernel-Mode Driver Architecture], PCLFS_MGMT_CLIENT_REGISTRATION, PCLFS_MGMT_CLIENT_REGISTRATION structure pointer [Kernel-Mode Driver Architecture], _CLFS_MGMT_CLIENT_REGISTRATION, kernel.clfs_mgmt_client_registration, kstruct_a_b4089ae7-0e80-4da0-b062-cda3d5aa65f4.xml, wdm/CLFS_MGMT_CLIENT_REGISTRATION, wdm/PCLFS_MGMT_CLIENT_REGISTRATION"
f1_keywords:
 - "wdm/CLFS_MGMT_CLIENT_REGISTRATION"
req.header: wdm.h
req.include-header: Wdm.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- CLFS_MGMT_CLIENT_REGISTRATION
product:
- Windows
targetos: Windows
req.typenames: CLFS_MGMT_CLIENT_REGISTRATION, *PCLFS_MGMT_CLIENT_REGISTRATION
---

# _CLFS_MGMT_CLIENT_REGISTRATION structure


## -description


The <b>CLFS_MGMT_CLIENT_REGISTRATION</b> structure is given to CLFS management by clients who manage their own logs.


## -struct-fields




### -field Version

The version of the <b>CLFS_MGMT_CLIENT_REGISTRATION</b> structure. Set this to <b>CLFS_MGMT_CLIENT_REGISTRATION_VERSION</b>.


### -field AdvanceTailCallback

A pointer to the log's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_advance_tail_callback">ClfsAdvanceTailCallback</a> function.


### -field AdvanceTailCallbackData

A pointer to user-defined data that will be supplied to the <i>ClfsAdvanceTailCallback</i> function when the function is invoked. 


### -field LogGrowthCompleteCallback

A pointer to the log's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a> function.


### -field LogGrowthCompleteCallbackData

A pointer to user-defined data that will be supplied to the <i>ClfsLogGrowthCompleteCallback</i> function when the function is invoked. 


### -field LogUnpinnedCallback

A pointer to the log's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_log_unpinned_callback">ClfsLogUnpinnedCallback</a> function.


### -field LogUnpinnedCallbackData

A pointer to user-defined data that will be supplied to the <i>ClfsLogUnpinnedCallback</i> function when the function is invoked. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_advance_tail_callback">ClfsAdvanceTailCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_lff_handler_complete_callback">ClfsLogGrowthCompleteCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pclfs_client_log_unpinned_callback">ClfsLogUnpinnedCallback</a>
 

 

