---
UID: NA:netdispumdddi
ms.assetid: 1d7e00a7-9659-3240-83d0-8e90cdbbd29a
ms.author: windowsdriverdev
ms.date: 04/02/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netdispumdddi.h header


## -description


This header is used by display. For more information, see:

- [Display](../_display/index.md)

The reference pages in this section describe wireless display (Miracast) user-mode functions that the operating system  implements. Only Miracast user-mode drivers can call these functions. For functions that the Miracast user-mode driver implements, see Wireless Display (Miracast) Functions Implemented By User-Mode Drivers.

Pointers to the Miracast display callback functions are returned in a MIRACAST_CALLBACKS structure.


In this section


Topic
Description




PFN_GET_NEXT_CHUNK_DATA



Provides info about the next Miracast encode chunk that was reported to the Microsoft DirectX graphics kernel subsystem when the DXGK_INTERRUPT_TYPE interrupt type is  DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE.
The data type of this function is PFN_GET_NEXT_CHUNK_DATA.





PFN_MIRACAST_IO_CONTROL



Called by the user-mode display driver to send the kernel-mode  display miniport driver a synchronous I/O control request.
The data type of this function is PFN_MIRACAST_IO_CONTROL.





PFN_REGISTER_DATARATE_NOTIFICATIONS



Called by the user-mode driver to register with the operating system to receive network quality of service (QoS) notifications and the current  network bandwidth of the Miracast connection.
The data type of this function is PFN_REGISTER_DATARATE_NOTIFICATIONS.





PFN_REPORT_SESSION_STATUS



Called by the user-mode display driver to report the status of the current Miracast connected session.
The data type of this function is PFN_REPORT_SESSION_STATUS.





PFN_REPORT_STATISTIC



Called by the user-mode display driver to report the statistics of the Miracast link to the operating system.
The data type of this function is PFN_REPORT_STATISTIC.



 


Send comments about this topic to Microsoft

