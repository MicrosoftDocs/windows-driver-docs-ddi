---
UID: NS:wwan._WWAN_UICC_APP_LIST
title: _WWAN_UICC_APP_LIST (wwan.h)
description: The WWAN_UICC_APP_LIST structure describes a list of applications in a UICC and information about them. 
tech.root: netvista
ms.assetid: 79DAD0BC-171D-4930-BF62-A3F2BEEC7C69
ms.date: 04/08/2019
keywords: ["_WWAN_UICC_APP_LIST structure"]
f1_keywords:
 - "wwan/_WWAN_UICC_APP_LIST"
ms.keywords: _WWAN_UICC_APP_LIST, WWAN_UICC_APP_LIST, *PWWAN_UICC_APP_LIST, 
req.header: wwan.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: WWAN_UICC_APP_LIST, *PWWAN_UICC_APP_LIST
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- wwan.h
api_name: 
- _WWAN_UICC_APP_LIST
product:
- Windows
targetos: Windows
ms.custom: 19H1
---

# _WWAN_UICC_APP_LIST structure

## -description

The **WWAN_UICC_APP_LIST** structure describes a list of applications in a UICC and information about them. 

## -struct-fields

### -field Version

The version number of the structure that follows. In Windows 10, version 1903, this version must be set to **1**.
 
### -field AppCount

The number of UICC application [**WWAN_UICC_APP_INFO**](../wwan/ns-wwan-_wwan_uicc_app_info.md) structures being returned in this response.
 
### -field ActiveAppIndex

The index of the application selected by the modem for registration with the mobile network. This field must be between **0** and **AppCount - 1**. It indexes into the array of applications returned by this response. If no application is selected for registration, this field contains **0xFFFFFFFF**.
 
### -field AppListSize

The size of the app list data, in bytes.

### -field Response

An array of [**WWAN_UICC_APP_INFO**](../wwan/ns-wwan-_wwan_uicc_app_info.md) structures that represent the UICC application list response. Cast this member to **WWAN_UICC_APP_INFO** when retrieving information about an application.

## -remarks

This structure is used in the [**NDIS_WWAN_UICC_APP_LIST**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_app_list.md) structure.

## -see-also

[MB UICC application and file system access](https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-application-and-file-system-access)

[OID_WWAN_UICC_APP_LIST](https://docs.microsoft.com/windows-hardware/drivers/network/oid-wwan-uicc-app-list)

[**NDIS_WWAN_UICC_APP_LIST**](../ndiswwan/ns-ndiswwan-_ndis_wwan_uicc_app_list.md)
