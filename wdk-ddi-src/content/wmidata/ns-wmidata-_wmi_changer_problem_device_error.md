---
UID: NS:wmidata._WMI_CHANGER_PROBLEM_DEVICE_ERROR
title: "_WMI_CHANGER_PROBLEM_DEVICE_ERROR" (wmidata.h)
description: When the ChangerPerformDiagnostics routine performs diagnostic tests on a changer device it returns the results in a WMI_CHANGER_PROBLEM_DEVICE_ERROR structure.
old-location: storage\wmi_changer_problem_device_error.htm
tech.root: storage
ms.assetid: c2c0f2eb-cb35-4f23-beb6-7f0eaeda845a
ms.date: 02/26/2018
ms.keywords: "*PWMI_CHANGER_PROBLEM_DEVICE_ERROR, PWMI_CHANGER_PROBLEM_DEVICE_ERROR, PWMI_CHANGER_PROBLEM_DEVICE_ERROR structure pointer [Storage Devices], WMI_CHANGER_PROBLEM_DEVICE_ERROR, WMI_CHANGER_PROBLEM_DEVICE_ERROR structure [Storage Devices], _WMI_CHANGER_PROBLEM_DEVICE_ERROR, storage.wmi_changer_problem_device_error, structs-changer_0d8bac8e-b24c-4ff8-948e-0dd55b5624f0.xml, wmidata/PWMI_CHANGER_PROBLEM_DEVICE_ERROR, wmidata/WMI_CHANGER_PROBLEM_DEVICE_ERROR"
ms.topic: struct
req.header: wmidata.h
req.include-header:
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
-	wmidata.h
api_name:
-	WMI_CHANGER_PROBLEM_DEVICE_ERROR
product:
- Windows
targetos: Windows
req.typenames: WMI_CHANGER_PROBLEM_DEVICE_ERROR, *PWMI_CHANGER_PROBLEM_DEVICE_ERROR
req.product: Windows 10 or later.
---

# _WMI_CHANGER_PROBLEM_DEVICE_ERROR structure


## -description


When the <a href="..\mcd\nf-mcd-changerperformdiagnostics.md">ChangerPerformDiagnostics</a> routine performs diagnostic tests on a changer device it returns the results in a WMI_CHANGER_PROBLEM_DEVICE_ERROR structure.


## -syntax


```cpp
typedef struct _WMI_CHANGER_PROBLEM_DEVICE_ERROR {
  ULONG ChangerProblemType;
} WMI_CHANGER_PROBLEM_DEVICE_ERROR, *PWMI_CHANGER_PROBLEM_DEVICE_ERROR;
```


## -struct-fields




### -field ChangerProblemType

Contains one of the enumeration values defined for the <a href="..\ntddchgr\ne-ntddchgr-_changer_device_problem_type.md">CHANGER_DEVICE_PROBLEM_TYPE</a> enumeration data type. The minidriver sets <b>ChangerProblemType</b> to the appropriate enumerator value.


## -see-also

<a href="..\ntddchgr\ne-ntddchgr-_changer_device_problem_type.md">CHANGER_DEVICE_PROBLEM_TYPE</a>



<a href="..\mcd\nf-mcd-changerperformdiagnostics.md">ChangerPerformDiagnostics</a>



 

 


