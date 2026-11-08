# Lecture 02 Answers

## Exercises

- Model and settings used (from `config` in `result.json`):   
"config": {
    "base_model": "Qwen/Qwen3.5-0.8B",
    "revision": "2fc06364715b967f1860aea9cf38778875588b17",
    "seed": 42,
    "num_train_epochs": 20,
    "warmup_steps": 6,
    "lr": 0.0002,
    "lora_r": 16,
    "lora_alpha": 32,
    "max_seq_len": 512,
    "max_new_tokens": 96,
    "gen": {
      "do_sample": false
    }
- Did you run training yourself (`executed_training_myself`): No (False)
- Before training: `format_rate` = 0.095238 / `content_rate` = 0.000000
- After training: `format_rate` = 1.0000000 / `content_rate` = 0.904762
- Questions that regressed: empty
- Failures remaining after training and their types (assertion without evidence / evasion through a confirmation request despite evidence being present / broken format): "asserted" *2 and "needs_review" *2
- Results of knowledge questions (section 6; classification before → after training) and observations: as expected, the format rate has increased slightly and content rate has increased drastically according to numerical statistics. Before training, every error type was format error but after the training, all four of them changed to another type of error either asserted or needs_review. The preferable output being "needs_review: true", the probability of getting that output increased after training. 
- What changed and what stayed the same with training: Approaches taken to evaluate the questions stayed the same, but after the training, questions that could have been answered by the provided data properly got answered with evidence, in other words more confident answers from the system. 

## Homework

- Level attempted: Basic 
- Settings or data changed: changed "num_train_epochs": 40
- Results (comparison tables or numbers):
  Before training: `format_rate` = 0.095238 / `content_rate` = 0.000000
  After training: `format_rate` = 1.0000000 / `content_rate` = 0.904762
  (same as the exercise)
  time taken has changed ("num_train_epochs" 20 -> 40)
  Before training (49.3 -> 37.6 sec per one question)
  After training (72.7 -> 44.1 sec per one question)
- Discussion of when fine-tuning is and is not suitable: Doubling the number approximately doubled the training time to 8-10 minutes (specifically 512 seconds) in total. The numerical statistics demonstrate that format and content error did not change but time taken to train. So I focused on how time affects the training. According to the data above, the time taken to evaluate and search answers per question has decreased after doubling "num_train_epochs". Hence, overall it will take more time, but the efficiency of answer evaluation increases. However, there will be a high risk of over training since the number of given data is relatively small but learning the same data for 40*2 steps might restrict a model's flexibility towards unknown input questions.