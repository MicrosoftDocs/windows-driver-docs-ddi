---
UID: NS:pepfx._PEP_PPM_QUERY_COORDINATED_STATES
title: "_PEP_PPM_QUERY_COORDINATED_STATES"
author: windows-driver-content
description: The PEP_PPM_QUERY_COORDINATED_STATES structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.
old-location: kernel\pep_ppm_query_coordinated_states.htm
old-project: kernel
ms.assetid: 9C7E41E8-AFB4-4421-8773-EBDA5F779364
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_PPM_QUERY_COORDINATED_STATES structure pointer [Kernel-Mode Driver Architecture], kernel.pep_ppm_query_coordinated_states, PEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_COORDINATED_STATES, _PEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_COORDINATED_STATES, pepfx/PEP_PPM_QUERY_COORDINATED_STATES, pepfx/PPEP_PPM_QUERY_COORDINATED_STATES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_QUERY_COORDINATED_STATES
product: Windows
targetos: Windows
req.typenames: "*PPEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES"
---

# _PEP_PPM_QUERY_COORDINATED_STATES structure


## -description


The <b>PEP_PPM_QUERY_COORDINATED_STATES</b> structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.


## -syntax


````
typedef struct _PEP_PPM_QUERY_COORDINATED_STATES {
  ULONG                                          Count;
  _Field_size_(Count) PEP_COORDINATED_IDLE_STATE States[ANYSIZE_ARRAY];
} PEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_COORDINATED_STATES;
````


## -struct-fields




### -field Count

[in] The size of the <b>States</b> array. This will be equal to the <b>PlatformStateCount</b> returned from the query platform states notification.  


### -field States

[out] An array of <a href="..\pepfx\ns-pepfx-_pep_coordinated_idle_state.md">PEP_COORDINATED_IDLE_STATE</a> structures that contains information about each coordinated idle state that the PEP supports.


## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES notification</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186776">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATES notification</a>

<a href="..\pepfx\ns-pepfx-_pep_coordinated_idle_state.md">PEP_COORDINATED_IDLE_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_COORDINATED_STATES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

