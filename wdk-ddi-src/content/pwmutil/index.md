---
UID: NA:pwmutil
title: Pwmutil.h header
ms.assetid: b99cfd83-b486-3074-858e-6a79e4967733
ms.date: 05/09/2018
keywords: ["Pwmutil.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: spb
f1_keywords:
 - pwmutil
 - pwmutil/pwmutil
api_name:
 - pwmutil
---

# Pwmutil.h header


## -description

This header provides Pulse Width Modulator (PWM) helper routines for use by kernel-mode drivers. Drivers should use the function to parse and validate pin paths and extract the pin number.

To provide access to a Pulse width modulation (PWM) controller that is part of the SoC and memory-mapped to the SoC address space, you need to write a kernel-mode driver. For more information, see [PWM driver for an on-SoC PWM module](/windows-hardware/drivers/spb/pulse-width-controller driver?branch=spb).

An app can send requests to the controller driver by sending [PWM IOCTLs requests](/windows-hardware/drivers/spb/pulse-width-controller driver#pwm-ioctl-requests).

