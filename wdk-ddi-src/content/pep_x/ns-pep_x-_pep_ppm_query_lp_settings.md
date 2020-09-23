---
UID: NS:pep_x._PEP_PPM_QUERY_LP_SETTINGS
title: _PEP_PPM_QUERY_LP_SETTINGS (pep_x.h)
description: The PEP_PPM_QUERY_LP_SETTINGS structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.
old-location: kernel\pep_ppm_query_lp_settings.htm
tech.root: kernel
ms.assetid: 69A8792B-954E-49AF-A306-25B94183E58A
ms.date: 04/30/2018
keywords: ["PEP_PPM_QUERY_LP_SETTINGS structure"]
ms.keywords: "*PPEP_PPM_QUERY_LP_SETTINGS, PEP_PPM_QUERY_LP_SETTINGS, PEP_PPM_QUERY_LP_SETTINGS structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_LP_SETTINGS, PPEP_PPM_QUERY_LP_SETTINGS structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_LP_SETTINGS, kernel.pep_ppm_query_lp_settings, pep_x/PEP_PPM_QUERY_LP_SETTINGS, pep_x/PPEP_PPM_QUERY_LP_SETTINGS"
req.header: pep_x.h
req.include-header: Pepfx.h
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
req.irql: 
targetos: Windows
req.typenames: PEP_PPM_QUERY_LP_SETTINGS, *PPEP_PPM_QUERY_LP_SETTINGS
f1_keywords:
 - _PEP_PPM_QUERY_LP_SETTINGS
 - pep_x/_PEP_PPM_QUERY_LP_SETTINGS
 - PPEP_PPM_QUERY_LP_SETTINGS
 - pep_x/PPEP_PPM_QUERY_LP_SETTINGS
 - PEP_PPM_QUERY_LP_SETTINGS
 - pep_x/PEP_PPM_QUERY_LP_SETTINGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pep_x.h
api_name:
 - PEP_PPM_QUERY_LP_SETTINGS
---

# _PEP_PPM_QUERY_LP_SETTINGS structure


## -description

The <b>PEP_PPM_QUERY_LP_SETTINGS</b> structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.

## -struct-fields

### -field RegistryRoot

[out] The kernel handle to the registry root that contains the settings for a platform power scenario. For more information, see Remarks.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_query_lp_settings">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a> notification. The <b>RegistryRoot</b> member contains an output value that the PEP writes to the structure in response to this notification.

The PEP can provide settings for certain key power scenarios such as full-screen video playback and connected standby that have unique characteristics that can benefit from specially tuned power policies that are different from the default settings used by Windows. The PEP loads the settings for such a power scenario into the registry and passes the registry key for these settings to the operating system.

## -see-also

<a href="/windows-hardware/drivers/ddi/pep_x/ns-pep_x-_pep_ppm_query_lp_settings">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a>