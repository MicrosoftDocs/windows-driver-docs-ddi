---
UID: NS:pepfx._PEP_PPM_QUERY_VETO_REASON
title: "_PEP_PPM_QUERY_VETO_REASON"
author: windows-driver-content
description: The PEP_PPM_QUERY_VETO_REASON structure supplies a wide-character, null-terminated string that contains a descriptive, human-readable name for a veto reason.
old-location: kernel\pep_ppm_query_veto_reason.htm
old-project: kernel
ms.assetid: 21716141-487B-4950-A55D-C9EE3B8C8612
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_QUERY_VETO_REASON, PEP_PPM_QUERY_VETO_REASON, PEP_PPM_QUERY_VETO_REASON structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_VETO_REASON, PPEP_PPM_QUERY_VETO_REASON structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_VETO_REASON, kernel.pep_ppm_query_veto_reason, pepfx/PEP_PPM_QUERY_VETO_REASON, pepfx/PPEP_PPM_QUERY_VETO_REASON"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PPM_QUERY_VETO_REASON
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_VETO_REASON, *PPEP_PPM_QUERY_VETO_REASON
---

# _PEP_PPM_QUERY_VETO_REASON structure


## -description


The <b>PEP_PPM_QUERY_VETO_REASON</b> structure supplies a wide-character, null-terminated string that contains a descriptive, human-readable name for a veto reason.


## -struct-fields




### -field VetoReason

[in] The index that identifies this veto reason. If the platform extension plug-in (PEP) supports N veto reasons, valid veto reason indexes range from 1 to N. The PEP previously specified the number of supported veto reasons in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a> notification.


### -field NameSize

[out] The size, in bytes, of the string buffer pointed to by the <b>Name</b> member. This string size includes the storage space for the null character that terminates the wide-character string.


### -field Name

[in] A pointer to a PoFx-allocated string buffer. If this buffer pointer is non-<b>NULL</b>, the PEP writes a wide-character, null-terminated string to the buffer (and writes nothing to the <b>NameSize</b> member). Otherwise, the PEP writes nothing to this buffer and instead writes the required string size to the <b>NameSize</b> member.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASON</a> notification. The <b>VetoReason</b> and <b>Name</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). If the input value of the <b>Name</b> member is <b>NULL</b>, the PEP writes an output value (the required string buffer size) to the <b>NameSize</b> member.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASON</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a>
 

 

