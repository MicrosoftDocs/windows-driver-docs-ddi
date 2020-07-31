---
UID: NF:wdfinstaller.WDF_COINSTALLER_INSTALL_OPTIONS_INIT
title: WDF_COINSTALLER_INSTALL_OPTIONS_INIT function (wdfinstaller.h)
description: The WDF_COINSTALLER_INSTALL_OPTIONS_INIT function initializes a WDF_COINSTALLER_INSTALL_OPTIONS structure.
old-location: wdf\wdf_coinstaller_install_options_init.htm
tech.root: wdf
ms.assetid: 65fd2c27-7d9e-4dad-adef-8cb2bea9d9f2
ms.date: 02/26/2018
keywords: ["WDF_COINSTALLER_INSTALL_OPTIONS_INIT function"]
ms.keywords: DFCoinstallerRef_7a993590-87f2-4613-93d4-ffbc76672d8e.xml, WDF_COINSTALLER_INSTALL_OPTIONS_INIT, WDF_COINSTALLER_INSTALL_OPTIONS_INIT function, kmdf.wdf_coinstaller_install_options_init, wdf.wdf_coinstaller_install_options_init, wdfinstaller/WDF_COINSTALLER_INSTALL_OPTIONS_INIT
f1_keywords:
 - "wdfinstaller/WDF_COINSTALLER_INSTALL_OPTIONS_INIT"
 - "WDF_COINSTALLER_INSTALL_OPTIONS_INIT"
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
- wdfinstaller.h
api_name:
- WDF_COINSTALLER_INSTALL_OPTIONS_INIT
targetos: Windows
req.typenames: 
---

# WDF_COINSTALLER_INSTALL_OPTIONS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_COINSTALLER_INSTALL_OPTIONS_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/ns-wdfinstaller-_wdf_coinstaller_install_options">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure.


## -parameters




### -param ClientOptions [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/ns-wdfinstaller-_wdf_coinstaller_install_options">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure.


## -remarks



The <b>WDF_COINSTALLER_INSTALL_OPTIONS_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/ns-wdfinstaller-_wdf_coinstaller_install_options">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/ns-wdfinstaller-_wdf_coinstaller_install_options">WDF_COINSTALLER_INSTALL_OPTIONS</a> structure.

```cpp
WDF_COINSTALLER_INSTALL_OPTIONS clientOptions;
WDF_COINSTALLER_INSTALL_OPTIONS_INIT(&clientOptions);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfinstaller/ns-wdfinstaller-_wdf_coinstaller_install_options">WDF_COINSTALLER_INSTALL_OPTIONS</a>
 

 

