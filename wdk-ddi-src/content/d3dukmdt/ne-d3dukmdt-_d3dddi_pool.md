---
UID: NE:d3dukmdt._D3DDDI_POOL
title: "_D3DDDI_POOL"
author: windows-driver-content
description: The D3DDDI_POOL enumeration type contains values that identify particular types of memory pool.
old-location: display\d3dddi_pool.htm
old-project: display
ms.assetid: b3f34183-7595-47b6-a2f1-c32650734a04
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 3, D, D3DDDIPOOL_LOCALVIDMEM, D3DDDIPOOL_NONLOCALVIDMEM, D3DDDIPOOL_STAGINGMEM, D3DDDIPOOL_SYSTEMMEM, D3DDDIPOOL_VIDEOMEMORY, D3DDDI_POOL, D3DDDI_POOL enumeration [Display Devices], D3D_other_Structs_859cbea4-6000-4906-a3f4-3ff6ea4caa7b.xml, I, L, O, P, _, _D3DDDI_POOL, d3dukmdt/D3DDDIPOOL_LOCALVIDMEM, d3dukmdt/D3DDDIPOOL_NONLOCALVIDMEM, d3dukmdt/D3DDDIPOOL_STAGINGMEM, d3dukmdt/D3DDDIPOOL_SYSTEMMEM, d3dukmdt/D3DDDIPOOL_VIDEOMEMORY, d3dukmdt/D3DDDI_POOL, display.d3dddi_pool"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDI_POOL
product: Windows
targetos: Windows
req.typenames: D3DDDI_POOL
---

# _D3DDDI_POOL enumeration


## -description


The D3DDDI_POOL enumeration type contains values that identify particular types of memory pool.


## -syntax


````
typedef enum _D3DDDI_POOL { 
  D3DDDIPOOL_SYSTEMMEM       = 1,
  D3DDDIPOOL_VIDEOMEMORY     = 2,
  D3DDDIPOOL_LOCALVIDMEM     = 3,
  D3DDDIPOOL_NONLOCALVIDMEM  = 4,
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  D3DDDIPOOL_STAGINGMEM      = 5

#endif } D3DDDI_POOL;
````


## -enum-fields




### -field D3DDDIPOOL_SYSTEMMEM

Resources exist in system memory.


### -field D3DDDIPOOL_VIDEOMEMORY

Resources exist in display memory.


### -field D3DDDIPOOL_LOCALVIDMEM

Resources exist in true, local display memory rather than nonlocal display memory (for example, AGP memory).


### -field D3DDDIPOOL_NONLOCALVIDMEM

Resources exist in nonlocal display memory (for example, AGP memory) rather than true, local display memory.


### -field D3DDDIPOOL_STAGINGMEM

Resources exist in staging memory that the user-mode display driver has allocated. This value indicates to the driver that it should allocate its own staging memory rather than use allocated Direct3D 10Level 9 memory.

Must be supported by WDDM 1.3 and later drivers. Available starting with Windows 8.1.


## -remarks



Pool memory types are defined as an enumeration type rather than separate flags because the types are all mutually exclusive.

Note that the D3DDDIPOOL_LOCALVIDMEM and D3DDDIPOOL_NONLOCALVIDMEM values are provided as hints to the user-mode display driver so it can improve performance. For more information about these values, see <a href="https://msdn.microsoft.com/b4691de0-d3c9-4a6f-a9f4-aafb22ea3e97">Specifying Memory Type for a Resource</a>.




## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_POOL enumeration%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

