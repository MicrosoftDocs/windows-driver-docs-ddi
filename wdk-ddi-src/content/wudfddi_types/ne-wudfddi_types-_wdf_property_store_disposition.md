---
UID: NE:wudfddi_types._WDF_PROPERTY_STORE_DISPOSITION
title: "_WDF_PROPERTY_STORE_DISPOSITION"
author: windows-driver-content
description: The WDF_PROPERTY_STORE_DISPOSITION enumeration contains values that indicate whether a registry value was created or already existed when a driver obtained a property store interface.
old-location: wdf\wdf_property_store_disposition.htm
tech.root: wdf
ms.assetid: 107b55f5-0c06-45cc-9cbb-ba9e2fbca1e4
ms.date: 02/26/2018
ms.keywords: CreatedNewStore, OpenedExistingStore, WDF_PROPERTY_STORE_DISPOSITION, WDF_PROPERTY_STORE_DISPOSITION enumeration, _WDF_PROPERTY_STORE_DISPOSITION, umdf.wdf_property_store_disposition, umdfstructs_a25f5c08-88c9-41c0-9bab-023ea91d0a22.xml, wdf.wdf_property_store_disposition, wudfddi_types/CreatedNewStore, wudfddi_types/OpenedExistingStore, wudfddi_types/WDF_PROPERTY_STORE_DISPOSITION
ms.topic: enum
req.header: wudfddi_types.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_types.h
api_name:
-	WDF_PROPERTY_STORE_DISPOSITION
product:
- Windows
targetos: Windows
req.typenames: WDF_PROPERTY_STORE_DISPOSITION
---

# _WDF_PROPERTY_STORE_DISPOSITION enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PROPERTY_STORE_DISPOSITION</b> enumeration contains values that indicate whether a registry value was created or already existed when a driver obtained a property store interface.


## -enum-fields




### -field CreatedNewStore

The device property store (registry value) was created.


### -field OpenedExistingStore

The device property store already exists.


## -remarks



The <b>WDF_PROPERTY_STORE_DISPOSITION</b> enumeration is used as output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> methods.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>
 

 

