..    TODO/Review: {{review|partial=X}}.

*************
Action Editor
*************


The *Action Editor* enables you to see and edit the F-Curve data-blocks you defined
as :doc:`Actions </animation/actions>` in the *F-Curve Editor*.
So it takes place somewhere in-between the low-level
:doc:`F-Curves </editors/graph_editor/introduction>`, and the high-level :doc:`NLA editor </editors/nla/index>`.

It gives you a slightly simplified view of the F-Curve data-blocks
(somewhat similar to F-Curve drawn without handles).
The editor can lists all Action data-blocks of an object at once.

Each Action data-block forms a top-level channel (see below).
Note that an object can have several *Constraint* (one per animated constraint)
and *Pose* (for armatures, one per animated bone) F-Curve data-blocks,
and hence an action can have several of these channels.

..
   :doc:`Action constraint </rigging/constraints/relationship/action>` or
   the :doc:`pose libraries </rigging/armatures/properties/pose_library>`

.. figure:: /images/editors_dopesheet_action-editor.png

   The Action Editor.


Header
======

Layer Previous/Next (down/up arrow peak icon)
   Switch between different actions stacked/stashed on top of each other in the NLA Stack,
   without having to go to the NLA Editor and leaving tweak mode and reentering it on the other strip.

   Clicking on the up/down arrow buttons to go to the action in the NLA Track above/below the NLA Strip being
   whose action is being tweaked in the Action Editor.

   If there are multiple actions/strips on the same layer/track,
   then only the one closest to the current frame will be used.

   The operators will take into account the settings to view/edit the action in isolation (i.e. Solo and NLA Muting).
   This was done to make it easier to preview different stashed actions.

   - If moving from a solo'd NLA Track to the active action,
     the NLA stack will be muted so that the action can be edited in isolation.
   - Likewise, if the NLA stack is muted when editing the action,
     the NLA Track below it will be edited with solo enabled.
   - If switching between NLA Tracks, the solo status for the previous track will be transferred to the new track.

   .. note::

      These still work when you're not editing the action used by a NLA Strip.
      If you're just animating a new action normally,
      it is possible to use the "down arrow" to temporarily jump down to the previous action
      without losing the new action you're working on, and then use the "up arrow" to get back to
      it once you're done checking the other action(s).

.. _dopesheet-action-action:

Action
   A :ref:`Data-block menu <ui-data-block>`.

   Add ``+``
      When an action is created it is stored in a NLA Action Stash.
   Unlink ``X``
      When :kbd:`Shift-LMB` clicking it clears the Fake User and
      removes the stashed action from the NLA stack too.
Push Down (double down arrow peak icon)
   Adds the active action on to the NLA stack as a contributing strip.
   This is basically the same as pressing the Push Down button in the NLA Editor.
Stash (Snowflake icon)
   Stashes the active action on to the NLA stack. i.e. it is added as a non-contributing stack
   in the same way that it would if you were creating a new action instead.

.. note::

   In both of these cases (Push Down and Stash), once the action has been added to the NLA stack,
   it is cleared/unassigned from the active action slot
   (i.e. it cannot be edited anymore from the Action/Graph Editors,
   unless you enter "Tweak Mode" on the corresponding strips later).
