---
UID: NA:videoagp
ms.assetid: 0fc9df98-c623-3890-a8d0-1ec564589343
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Videoagp.h header



This header is used by Display. For more information, see
- [Display](../_display/index.md)

This section contains reference pages for the following AGP functions that are implemented, but not exported, by the video port driver. 

Before the video miniport driver can call the AGP functions, it must obtain function pointers by passing VideoPortServicesAgp to the VideoPortQueryServices function. The video miniport driver also passes a VIDEO_PORT_AGP_INTERFACE or VIDEO_PORT_AGP_INTERFACE_2 structure to VideoPortQueryServices. On return, that structure contains pointers to the AGP functions implemented by the video port driver.

For more information about AGP, see Video Port Driver Support for AGP.

For information about other sets of functions implemented by the video port driver, see the following topics:

Send comments about this topic to Microsoft

