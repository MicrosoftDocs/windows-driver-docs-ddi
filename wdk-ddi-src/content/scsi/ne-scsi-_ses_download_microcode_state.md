---
UID: NE:scsi._SES_DOWNLOAD_MICROCODE_STATE
title: "_SES_DOWNLOAD_MICROCODE_STATE"
author: windows-driver-content
description:
old-location: storage\ses_download_microcode_state.htm
tech.root: storage
ms.assetid: 5edff312-8373-4d36-b93c-c35fe8c2996a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSES_DOWNLOAD_MICROCODE_STATE, PSES_DOWNLOAD_MICROCODE_STATE, PSES_DOWNLOAD_MICROCODE_STATE enumeration pointer [Storage Devices], SES_DOWNLOAD_MICROCODE_STATE, SES_DOWNLOAD_MICROCODE_STATE enumeration [Storage Devices], SesDownloadMcStateCompletedPendingActivation, SesDownloadMcStateCompletedPendingPowerOn, SesDownloadMcStateCompletedPendingReset, SesDownloadMcStateInProgress, SesDownloadMcStateNoneInProgress, _SES_DOWNLOAD_MICROCODE_STATE, scsi/PSES_DOWNLOAD_MICROCODE_STATE, scsi/SES_DOWNLOAD_MICROCODE_STATE, scsi/SesDownloadMcStateCompletedPendingActivation, scsi/SesDownloadMcStateCompletedPendingPowerOn, scsi/SesDownloadMcStateCompletedPendingReset, scsi/SesDownloadMcStateInProgress, scsi/SesDownloadMcStateNoneInProgress, storage.ses_download_microcode_state"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: scsi.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
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
-	scsi.h
api_name:
-	SES_DOWNLOAD_MICROCODE_STATE
product:
- Windows
targetos: Windows
req.typenames: SES_DOWNLOAD_MICROCODE_STATE, *PSES_DOWNLOAD_MICROCODE_STATE
---

# _SES_DOWNLOAD_MICROCODE_STATE enumeration


## -description


The **SES_DOWNLOAD_MICROCODE_STATE** enumeration specifies the state of a microcode download operation.


## -enum-fields




### -field SesDownloadMcStateNoneInProgress

Specifies no microcode download operation is in progress.


### -field SesDownloadMcStateInProgress

Specifies a microcode download operation is in progress.


### -field SesDownloadMcStateCompletedPendingReset

Specifies a microcode download operation completed and is waiting for a hard reset.


### -field SesDownloadMcStateCompletedPendingPowerOn

Specifies a microcode download operation completed and is waiting for a power on.


### -field SesDownloadMcStateCompletedPendingActivation

Specifies a microcode download operation completed and is waiting for activation.

