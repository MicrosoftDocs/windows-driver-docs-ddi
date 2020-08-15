---
UID: NF:wdfregistry.WdfRegistryWdmGetHandle
title: WdfRegistryWdmGetHandle function (wdfregistry.h)
description: The WdfRegistryWdmGetHandle method returns a Windows Driver Model (WDM) handle to the registry key that a specified framework registry-key object represents.
old-location: wdf\wdfregistrywdmgethandle.htm
tech.root: wdf
ms.assetid: 60638048-9009-4943-ba61-b724612852df
ms.date: 02/26/2018
keywords: ["WdfRegistryWdmGetHandle function"]
ms.keywords: DFRegKeyObjectRef_9229cd7b-fb26-4e95-a5ee-5deb31f549f4.xml, WdfRegistryWdmGetHandle, WdfRegistryWdmGetHandle method, kmdf.wdfregistrywdmgethandle, wdf.wdfregistrywdmgethandle, wdfregistry/WdfRegistryWdmGetHandle
f1_keywords:
 - "wdfregistry/WdfRegistryWdmGetHandle"
 - "WdfRegistryWdmGetHandle"
req.header: wdfregistry.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfRegistryWdmGetHandle
targetos: Windows
req.typenames: 
---

# WdfRegistryWdmGetHandle function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryWdmGetHandle</b> method returns a Windows Driver Model (WDM) handle to the registry key that a specified framework registry-key object represents.


## -parameters




### -param Key 
[in]
A handle to a registry-key object that represents an opened registry key.


## -returns



<b>WdfRegistryWdmGetHandle</b> returns a WDM handle to a registry key. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A KMDF driver can pass the returned WDM handle to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">ZwXxx routines</a> that accept a WDM handle as input.

A UMDF driver can pass the returned handle to APIs that require an HKEY, such as <a href="https://docs.microsoft.com/windows/desktop/api/winreg/nf-winreg-regenumkeyexa">RegEnumKeyEx</a>.

The handle that the <b>WdfRegistryWdmGetHandle</b> method returns is valid until the registry-key object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the registry-key object, the pointer is valid until the callback function returns.

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example obtains a WDM handle to the registry key that a specified framework registry-key object represents.

```cpp
HANDLE hKey;

hKey = WdfRegistryWdmGetHandle(Key);
```


