---
UID: NE:wudfddi_types._WDF_PROPERTY_STORE_DISPOSITION
title: "_WDF_PROPERTY_STORE_DISPOSITION"
author: windows-driver-content
description: The WDF_PROPERTY_STORE_DISPOSITION enumeration contains values that indicate whether a registry value was created or already existed when a driver obtained a property store interface.
old-location: wdf\wdf_property_store_disposition.htm
old-project: wdf
ms.assetid: 107b55f5-0c06-45cc-9cbb-ba9e2fbca1e4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdf_property_store_disposition, CreatedNewStore, umdf.wdf_property_store_disposition, wudfddi_types/WDF_PROPERTY_STORE_DISPOSITION, WDF_PROPERTY_STORE_DISPOSITION, _WDF_PROPERTY_STORE_DISPOSITION, OpenedExistingStore, wudfddi_types/CreatedNewStore, wudfddi_types/OpenedExistingStore, umdfstructs_a25f5c08-88c9-41c0-9bab-023ea91d0a22.xml, WDF_PROPERTY_STORE_DISPOSITION enumeration
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_types.h
apiname:
-	WDF_PROPERTY_STORE_DISPOSITION
product: Windows
targetos: Windows
req.typenames: WDF_PROPERTY_STORE_DISPOSITION
req.product: Windows 10 or later.
---

# _WDF_PROPERTY_STORE_DISPOSITION enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PROPERTY_STORE_DISPOSITION</b> enumeration contains values that indicate whether a registry value was created or already existed when a driver obtained a property store interface.


## -syntax


````
typedef enum _WDF_PROPERTY_STORE_DISPOSITION { 
  CreatedNewStore      = 0x1,
  OpenedExistingStore  = 0x2
} WDF_PROPERTY_STORE_DISPOSITION;
````


## -enum-fields




### -field CreatedNewStore

The device property store (registry value) was created.


### -field OpenedExistingStore

The device property store already exists.


## -remarks


The <b>WDF_PROPERTY_STORE_DISPOSITION</b> enumeration is used as output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> methods.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558842">IWDFDevice::RetrieveDevicePropertyStore</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560228">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_PROPERTY_STORE_DISPOSITION enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

