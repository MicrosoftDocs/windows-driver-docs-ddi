---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO
title: IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO
author: windows-driver-content
description: The IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO request relinquishes control of band management by the Trusted Computing Group (TCG) Storage Silo driver.
old-location: storage\ioctl_ehstor_tcgdrv_relinquish_silo.htm
old-project: storage
ms.assetid: 4D3DA81A-D79A-4299-A743-AFB0118DDF3F
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO, IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO, storage.ioctl_ehstor_tcgdrv_relinquish_silo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
-	EhStorBandMgmt.h
apiname:
-	IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The <b>IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO</b> request relinquishes control of band management by the Trusted Computing Group (TCG) Storage Silo driver.  Applications issue this request to manage a storage silo directly. The band management functionality and API provided by the TCG Storage Silo driver are disabled.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

On return, the <b>Status</b> field will contain STATUS_SUCCESS if the operation was successful. Otherwise, another appropriate status code is returned.


## -remarks



When the TCG Storage Silo driver relinquishes control, all band management IOCTLs registered by an <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities.md"> IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a> request are unregistered. Any band management IOCTL requests received are returned with STATUS_INVALID_DEVICE_REQUEST. 

After relinquishing control, the TCG Storage Silo driver can regain control of a storage device when the device is stopped and restarted.

To prevent the TCG Storage Silo driver from reconfiguring the TCG subsystem in a mode compatible with Windows after restart, the SID credential should be changed to a nondefault value or SID authority should be disabled. This will also allow direct management of a storage silo.




## -see-also

<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_driver_report_capabilities.md">IOCTL_EHSTOR_DRIVER_REPORT_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_TCGDRV_RELINQUISH_SILO control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

