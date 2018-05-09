---
UID: NS:iddcx.IDD_CX_CLIENT_CONFIG
title: IDD_CX_CLIENT_CONFIG
author: windows-driver-content
description: The IDD_CX_CLIENT_CONFIG structure contains IDDCX callback functions that the display driver can use.
old-location: display\idd_cx_client_config.htm
old-project: display
ms.assetid: 8e286cb2-87f4-483b-bc55-f174e7de5989
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IDD_CX_CLIENT_CONFIG, IDD_CX_CLIENT_CONFIG structure [Display Devices], display.idd_cx_client_config, iddcx/IDD_CX_CLIENT_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
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
-	iddcx.h
api_name:
-	IDD_CX_CLIENT_CONFIG
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDD_CX_CLIENT_CONFIG structure


## -description


The IDD_CX_CLIENT_CONFIG structure contains IDDCX callback functions that the display driver can use.


## -struct-fields




### -field Size


                     The total size of the structure.


### -field EvtIddCxDeviceIoControl


                     A pointer to the  <b>PFN_IDD_CX_DEVICE_IO_CONTROL</b> function.


### -field EvtIddCxParseMonitorDescription


                     A pointer to the  <b>PFN_IDD_CX_PARSE_MONITOR_DESCRIPTION</b> function.


### -field EvtIddCxAdapterInitFinished


                     A pointer to the  <b>PFN_IDD_CX_ADAPTER_INIT_FINISHED</b> function.


### -field EvtIddCxAdapterCommitModes


                     A pointer to the  <b>PFN_IDD_CX_ADAPTER_COMMIT_MODES</b> function.


### -field EvtIddCxMonitorGetDefaultDescriptionModes


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_GET_DEFAULT_DESCRIPTION_MODES</b> function.


### -field EvtIddCxMonitorQueryTargetModes


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_QUERY_TARGET_MODES</b> function.


### -field EvtIddCxMonitorAssignSwapChain


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_ASSIGN_SWAPCHAIN</b> function.


### -field EvtIddCxMonitorUnassignSwapChain


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_UNASSIGN_SWAPCHAIN</b> function.


### -field EvtIddCxMonitorI2CTransmit


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_I2C_TRANSMIT</b> function.


### -field EvtIddCxMonitorI2CReceive


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_I2C_RECEIVE</b> function.


### -field EvtIddCxMonitorSetGammaRamp


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_SET_GAMMA_RAMP</b> function.


### -field EvtIddCxMonitorOPMGetCertificateSize


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE_SIZE</b> function.


### -field EvtIddCxMonitorOPMGetCertificate


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE</b> function.


### -field EvtIddCxMonitorOPMCreateProtectedOutput


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_CREATE_PROTECTED_OUTPUT</b> function.


### -field EvtIddCxMonitorOPMGetRandomNumber


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_GET_RANDOM_NUMBER</b> function.


### -field EvtIddCxMonitorOPMSetSigningKeyAndSequenceNumbers


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_SET_SIGNING_KEY_AND_SEQUENCE_NUMBERS</b> function.


### -field EvtIddCxMonitorOPMGetInformation


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_GET_INFOMATION</b> function.


### -field EvtIddCxMonitorOPMConfigureProtectedOutput


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_CONFIGURE_PROTECTED_OUTPUT</b> function.


### -field EvtIddCxMonitorOPMDestroyProtectedOutput


                     A pointer to the  <b>PFN_IDD_CX_MONITOR_OPM_DESTROY_PROTECTED_OUTPUT</b> function.

