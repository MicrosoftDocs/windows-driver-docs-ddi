---
UID: NS:dispmprt._DXGK_TIMED_OPERATION
title: _DXGK_TIMED_OPERATION (dispmprt.h)
description: The DXGK_TIMED_OPERATION structure describes a timed operation, which is used in the Timed Operation Interface.
old-location: display\dxgk_timed_operation.htm
tech.root: display
ms.assetid: 6b377ba5-cd3b-433e-bd9c-315203c3bc69
ms.date: 05/10/2018
ms.keywords: "*PDXGK_TIMED_OPERATION, DXGK_TIMED_OPERATION, DXGK_TIMED_OPERATION structure [Display Devices], DmStructs_1d58055e-2e81-4a42-b596-390752f0db84.xml, PDXGK_TIMED_OPERATION, PDXGK_TIMED_OPERATION structure pointer [Display Devices], _DXGK_TIMED_OPERATION, display.dxgk_timed_operation, dispmprt/DXGK_TIMED_OPERATION, dispmprt/PDXGK_TIMED_OPERATION"
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- DXGK_TIMED_OPERATION
product:
- Windows
targetos: Windows
req.typenames: DXGK_TIMED_OPERATION, *PDXGK_TIMED_OPERATION
---

# _DXGK_TIMED_OPERATION structure


## -description


The DXGK_TIMED_OPERATION structure describes a timed operation, which is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>.


## -struct-fields




### -field Size

[in] The size, in bytes, of this structure.


### -field OwnerTag

[system] A pointer to the place in the code that started the timed operation.


### -field OsHandled

[system] For system use only. 


### -field TimeoutTriggered

[out] A Boolean value that specifies whether the time-out was triggered. 


### -field Timeout

[system] For system use only. 


### -field StartTick

[system] For system use only. 


## -remarks



Display miniport drivers should not change of rely on members that are marked with the  [system] designation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>
 

 

