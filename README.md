# Brain imaging and gambling advertising

PsychoPy task materials for an fMRI study comparing responses to gambling and non-gambling advertisements. The study aims to investigate how neural responses to these advertisements relate to depressive symptoms and gambling behaviour.

This repository contains three experiment runs, their condition tables, instructions for running the task, and documentation of the timing output. The implementation described here reflects the current experiment files from 14 November 2026. The study protocol and preregistration are being developed.

## Research context

The project overview proposes a within-participant comparison of gambling and non-gambling advertising in adults who gamble and experience depressive symptoms. Its primary research questions concern emotion-related and reward-related neural responses. Proposed exploratory work concerns rumination, emotion regulation, social connectedness, and gender-related beliefs.

These are study aims and proposed analyses. Final hypotheses, recruitment targets, eligibility criteria, measures, and analysis specifications will be documented in the agreed protocol and OSF preregistration.

## Current task

| Feature | Current implementation |
| --- | --- |
| Runs | Three separate PsychoPy experiments |
| Trials per run | 20: 10 gambling adverts and 10 non-gambling adverts |
| Trial order | Randomised within each run |
| Videos | Approximately 20 seconds each; the current files contain no audio streams |
| Instructions | 10 seconds; automatic progression |
| Start signal | Keyboard event `t`, after the instructions |
| Question | “How did this advert make you feel?” |
| Responses | `1` = Pleasant; `2` = Unpleasant |
| Question display | 3 seconds |
| Response collection | 5 seconds, including the 3-second question display |
| Timing output | One row per attempted video in a separate timing CSV |

The current condition tables reference the same 20 video filenames in all three runs. Each run uses its own condition table. Media hashes are recorded separately for each run; two Run 1 files (`N4_20sec.mp4` and `N9_20sec.mp4`) differ from the corresponding Run 2/3 files, so preserve the run-specific assets. The `Valence` field in those tables identifies advert category (`GAM` or `COM`); it does not contain the participant's Pleasant/Unpleasant response.

## Repository contents

- `Run1/run1_epi_mri_for_mc.psyexp` and `Run1/LoopTemplate_MRI_RUN1.xlsx`
- `Run2/run2_epi_mri_for_mc.psyexp` and `Run2/LoopTemplate_MRI_RUN2.xlsx`
- `Run3/run3_epi_mri_for_mc.psyexp` and `Run3/LoopTemplate_MRI_RUN3.xlsx`
- [Running the task](docs/running_the_task.md)
- [Timing output and response data](docs/timing_output.md)
- [Stimulus file manifest](docs/stimulus_manifest.json)
- [Protocol details to finalise](docs/protocol_status.md)

The Builder `.psyexp` files are the experiment source. PsychoPy generates the running Python scripts from them. Stimulus media must be supplied separately in each run's `Videos/` and `POS_stimuli/` folders. Local outputs are saved in each run's `data/` folder, which is excluded from version control.

## Software and validation

The current files were prepared using PsychoPy Standalone 2026.2.5 on macOS, with the ioHub keyboard backend and ffpyplayer movie backend. Run 1 has completed a local 20-video test; Run 2 and Run 3 have passed compilation and timing-logging checks. These checks do not establish scanner hardware timing.

A local Run 1 test lasted approximately 8 minutes 47 seconds from the accepted trigger to the end screen disappearing. This is an observed example, not a fixed duration guarantee. Instructions, waiting for the trigger, and breaks between runs add to the total session time.

The scanner trigger and response-box mapping must be checked on the experiment computer. The current configured inputs are `t`, `1`, and `2`.

## Project team

The project overview lists John McAlaney, Ala Yankouskaya, Emily Arden-Close, Ellen Seiss, Reece Bush, Ruijie Wang, Elvira Bolat, Alex Caton-Bradley, and Shannon Patton. Affiliations, repository maintainers, and preferred citation details are to be confirmed.

## Project status and reuse

An OSF preregistration link, ethics details, and the agreed code licence will be added when supplied. No code licence has been selected for this draft. Stimulus availability and permitted redistribution will be documented separately.
