---
UID: NF:wdfregistry.WdfRegistryClose
title: WdfRegistryClose function
author: windows-driver-content
description: The WdfRegistryClose method closes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.
old-location: wdf\wdfregistryclose.htm
old-project: wdf
ms.assetid: c97fe47d-bd6b-45d7-936b-3b46554e5093
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfregistry/WdfRegistryClose, DFRegKeyObjectRef_31a198b2-e149-4fd4-951a-5fd03cf06555.xml, wdf.wdfregistryclose, WdfRegistryClose method, kmdf.wdfregistryclose, PFN_WDFREGISTRYCLOSE, WdfRegistryClose
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRegistryClose
product: Windows
targetos: Windows
req.typenames: "*PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG"
req.product: Windows 10 or later.
---

# WdfRegistryClose function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRegistryClose</b> method closes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.


## -syntax


````
VOID WdfRegistryClose(
  _In_ WDFKEY Key
);
````


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


After your driver has finished accessing a registry key, it must call <b>WdfRegistryClose</b> or <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>. Both of these methods close the registry key and delete the registry-key object. 

For more information about registry-key objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in Framework-Based Drivers</a>.



## -see-also

<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRegistryClose method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

