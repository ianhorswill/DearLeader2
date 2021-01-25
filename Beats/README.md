This directory contains files that define story beats, i.e. atomic story events that aren't subdivided into smaller events:

- A beat must generate text.
- It may optionally also generate stage directions (see the stage directions directory).
- It generally should not call other tasks that describe independent events (because then this wouldn't be an indivisible beat)
- It must end with a call to [Beat] to mark it as the end of the beat.  

The call to [Beat] is used both by the profiler to find which tasks are beats, and also to 