---
title: areatrigger_template
description: This table contains the description of areatrigger.
published: true
date: 2022-12-24T04:48:16.572Z
tags: database, master, world
editor: markdown
dateCreated: 2021-08-30T09:28:59.429Z
---

<a href="https://trinitycore.info/en/database/master/world/areatrigger_teleport" class="mt-5 v-btn v-btn--depressed v-btn--flat v-btn--outlined theme--light v-size--default darkblue--text text--lighten-3"><span class="v-btn__content"><i aria-hidden="true" class="v-icon notranslate v-icon--left mdi mdi-arrow-left theme--light"></i><span>Back to 'areatrigger_teleport'</span></span></a>&nbsp;&nbsp;&nbsp;<a href="https://trinitycore.info/en/database/master/world/home" class="mt-5 v-btn v-btn--depressed v-btn--flat v-btn--outlined theme--light v-size--default darkblue--text text--lighten-3"><span class="v-btn__content"><i aria-hidden="true" class="v-icon notranslate v-icon--left mdi mdi-home-outline theme--light"></i><span>Return to world</span></span></a>&nbsp;&nbsp;&nbsp;<a href="https://trinitycore.info/en/database/master/world/areatrigger_template_actions" class="mt-5 v-btn v-btn--depressed v-btn--flat v-btn--outlined theme--light v-size--default darkblue--text text--lighten-3"><span class="v-btn__content"><span>Go to 'areatrigger_template_actions'</span><i aria-hidden="true" class="v-icon notranslate v-icon--right mdi mdi-arrow-right theme--light"></i></span></a>

## Structure

| Field | Type | Attributes | Key | Null | Default | Extra | Comment |
| --- | --- | --- | :---: | :---: | --- | --- | --- |
| [Id](#id) | int | unsigned | PRI | NO |  |  |  |
| [IsServerSide](#isserverside) | tinyint | unsigned | PRI | NO |  |  |  |
| [Type](#type) | tinyint | unsigned |  | NO | 0 |  |  |
| [Flags](#flags) | int | unsigned |  | NO | 0 |  |  |
| [Data0](#data0-7) | float |  |  | NO | 0 |  |  |
| [Data1](#data0-7) | float |  |  | NO | 0 |  |  |
| [Data2](#data0-7) | float |  |  | NO | 0 |  |  |
| [Data3](#data0-7) | float |  |  | NO | 0 |  |  |
| [Data4](#data0-7) | float |  |  | NO | 0 |  |  |
| [Data5](#data0-7) | float |  |  | NO | 0 |  |  |
| [Data6](#data0-7) | float |  |  | NO | 0 |  |  |
| [Data7](#data0-7) | float |  |  | NO | 0 |  |  |
| [VerifiedBuild](#verifiedbuild) | int | unsigned |  | NO | 0 |  |  |
&nbsp;
## Description of fields

### Id
Unique identifier
&nbsp;

### IsServerSide
0 = False
1 = True

If `True` then the data is not sent to client via `SMGS_UPDATE_OBJECT` packet (e.g. instance entries/exists)

Nevertheless there are still clientsided areatriggers for content before Legion addon.
You can see them inside [AreaTrigger.db2](https://wow.tools/dbc/?dbc=areatrigger){target=_blank}
&nbsp;

### Type
|ID|Name|
|:---:|---|
|0|AREATRIGGER_TYPE_SPHERE|
|1|AREATRIGGER_TYPE_BOX|
|2|AREATRIGGER_TYPE_UNK|
|3|AREATRIGGER_TYPE_POLYGON|
|4|AREATRIGGER_TYPE_CYLINDER|
|5|AREATRIGGER_TYPE_DISK|
|6|AREATRIGGER_TYPE_BOUNDED_PLANE|
&nbsp;

### Flags
|Flag|Name|
|---|--- |
|1|AREATRIGGER_FLAG_HAS_ABSOLUTE_ORIENTATION|
|2|AREATRIGGER_FLAG_HAS_DYNAMIC_SHAPE|
|4|AREATRIGGER_FLAG_HAS_ATTACHED|
|8|AREATRIGGER_FLAG_HAS_FACE_MOVEMENT_DIR|
|16|AREATRIGGER_FLAG_HAS_FOLLOWS_TERRAIN|
|32|AREATRIGGER_FLAG_UNK1|
|64|AREATRIGGER_FLAG_HAS_TARGET_ROLL_PITCH_YAW|
|128|AREATRIGGER_FLAG_HAS_ANIM_ID (DEPRECATED)|
|256|AREATRIGGER_FLAG_UNK3|
|512|AREATRIGGER_FLAG_HAS_ANIM_KIT_ID (DEPRECATED)|
|1024|AREATRIGGER_FLAG_HAS_CIRCULAR_MOVEMENT (DEPRECATED)|
|2048|AREATRIGGER_FLAG_UNK5
&nbsp;

### Data0-7
The data changes depending on the Type.
| |SPHERE|BOX|UNK|POLYGON|CYLINDER|DISK|BOUNDED PLANE
|:---:|---|---|---|---|---|---|---|
|Data0| Radius | ExtentsX | - | Height | Radius | InnerRadius | ExtentsX
|Data1| RadiusTarget | ExtentsY | - | HeightTarget | RadiusTarget | InnerRadiusTarget | ExtentsY
|Data2| - | ExtentsZ | - | - | Height | OuterRadius | ExtentsTargetX
|Data3| - | ExtentsTargetX | - | - | HeightTarget | OuterRadiusTarget | ExtentsTargetY
|Data4| - | ExtentsTargetY | - | - | LocationZOffset | Height | - 
|Data5| - | ExtentsTargetZ | - | - | LocationZOffsetTarget | HeightTarget | -
|Data6| - | - | - | - | -| LocationZOffset | -
|Data7| - | - | - | - | - | LocationZOffsetTarget | -
&nbsp;

### VerifiedBuild
This field is used by the TrinityDB Team to determine whether a template has been verified from WDB files.

If value is 0 then it has not been parsed yet.

If value is above 0 then it has been parsed with WDB files from that specific client build.

If value is -1 then it is just a place holder until proper data are found on WDBs.

If value is -Client Build then it was parsed with WDB files from that specific client build and manually edited later for some special necessity.

&nbsp;

<a href="https://trinitycore.info/en/database/master/world/areatrigger_teleport" class="mt-5 v-btn v-btn--depressed v-btn--flat v-btn--outlined theme--light v-size--default darkblue--text text--lighten-3"><span class="v-btn__content"><i aria-hidden="true" class="v-icon notranslate v-icon--left mdi mdi-arrow-left theme--light"></i><span>Back to 'areatrigger_teleport'</span></span></a>&nbsp;&nbsp;&nbsp;<a href="https://trinitycore.info/en/database/master/world/home" class="mt-5 v-btn v-btn--depressed v-btn--flat v-btn--outlined theme--light v-size--default darkblue--text text--lighten-3"><span class="v-btn__content"><i aria-hidden="true" class="v-icon notranslate v-icon--left mdi mdi-home-outline theme--light"></i><span>Return to world</span></span></a>&nbsp;&nbsp;&nbsp;<a href="https://trinitycore.info/en/database/master/world/areatrigger_template_actions" class="mt-5 v-btn v-btn--depressed v-btn--flat v-btn--outlined theme--light v-size--default darkblue--text text--lighten-3"><span class="v-btn__content"><span>Go to 'areatrigger_template_actions'</span><i aria-hidden="true" class="v-icon notranslate v-icon--right mdi mdi-arrow-right theme--light"></i></span></a>
