---
UID: NS:iddcx.IDARG_IN_I2C_RECEIVE
title: IDARG_IN_I2C_RECEIVE
author: windows-driver-content
description: Gives information about I2C data being received by the OS.
old-location: display\idarg_in_i2c_receive.htm
old-project: display
ms.assetid: a44a45bf-4c21-4507-a89b-4130622bdd06
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IDARG_IN_I2C_RECEIVE, IDARG_IN_I2C_RECEIVE structure [Display Devices], display.idarg_in_i2c_receive, iddcx/IDARG_IN_I2C_RECEIVE
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
-	IDARG_IN_I2C_RECEIVE
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_I2C_RECEIVE structure


## -description



                 Gives information about I2C data being received by the OS.


## -struct-fields




### -field SevenBitI2CAddress


                     [in] The address of the I2C device from which data will be received.
                 


### -field Flags


                     [in] Flags for the receive operation.
                 


### -field DataSizeInBytes


                     [in] The size, in bytes, of the buffer pointed to by <b>pData</b>.
                 


### -field pData


                     [out] A pointer to a buffer that receives the data.
                 

