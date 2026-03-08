# Latent Bridge output analysis summary

## Main result
In the current Qwen2.5-1.5B run, the strongest latent signal is English followed by the final target native script. Devanagari and Hindi lexical candidate sets remain near zero and never cross the RomanLens-style 0.1 latent-fraction threshold in the analyzed runs.

## First-step onset summary
| pair_name   |   english_mean_onset_first_step |   target_native_mean_onset_first_step |   english_frac_present_first_step |   target_native_frac_present_first_step |   english_mean_peak_mass_first_step |   target_native_mean_peak_mass_first_step |   devanagari_mean_peak_mass_first_step |   hindi_mean_peak_mass_first_step |
|:------------|--------------------------------:|--------------------------------------:|----------------------------------:|----------------------------------------:|------------------------------------:|------------------------------------------:|---------------------------------------:|----------------------------------:|
| asm_to_ben  |                          22     |                                26.2   |                             0.733 |                                       1 |                              0.5119 |                                    0.9024 |                                 0.0078 |                            0.0081 |
| ben_to_guj  |                          22.5   |                                25.533 |                             0.8   |                                       1 |                              0.3426 |                                    0.8855 |                                 0.0117 |                            0.0124 |
| guj_to_tam  |                          22.222 |                                23.867 |                             0.6   |                                       1 |                              0.4274 |                                    0.4617 |                                 0.0113 |                            0.0141 |
| hin_to_guj  |                          22.545 |                                25     |                             0.733 |                                       1 |                              0.2249 |                                    0.822  |                                 0.0359 |                            0.0411 |

## Sentence condition summary (mean chrF)
| pair_name   |   devanagari_source |   direct_native |   english_source |   hindi_source |   roman_source |
|:------------|--------------------:|----------------:|-----------------:|---------------:|---------------:|
| asm_to_ben  |              13.746 |          10.041 |           11.935 |          9.198 |         10.957 |
| ben_to_guj  |              11.485 |           9.136 |            8.632 |          9.214 |          8.918 |
| guj_to_tam  |              11.833 |           7.675 |           14.09  |         12.007 |         11.756 |
| hin_to_guj  |              14.329 |          13.212 |           12.799 |         13.212 |         11.419 |

## Patching summary (mean KL to native)
| pair_name   |   devanagari |    hindi |   native |    roman |
|:------------|-------------:|---------:|---------:|---------:|
| asm_to_ben  |     0.000164 | 0.000362 |        0 | 0.000662 |
| ben_to_guj  |     0.000195 | 0.000343 |        0 | 0.003697 |
| guj_to_tam  |     0.000356 | 0.000346 |        0 | 0.001672 |
| hin_to_guj  |     0        | 0        |        0 | 0.002961 |

## Tokenization warning
Decoded token pieces contain replacement characters for most sampled non-Latin words, so this model/tokenizer pair is not ideal for definitive negative claims about script routing.