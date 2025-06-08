## Tests

- If possible, prefer writing a test case for whatever you add, change or fix.
- Always run the whole test suite before submitting a new pull request.


## Coding Style

Keep indention and style consistency in mind and double-check your commit diffs before pushing.

### Definition
  * **Always:**
    * **End of line:** LF
    * **Insert final newline:** yes
  * **Python:**
    * **Indention:** 4 spaces
    * **Style:** full PEP except max line length on judgement (E501)
  * **HTML/CSS:**
     * **Indention:** 1 tab
  * **YAML:**
    * **Indention:** 2 spaces
  * **Markdown:**
    * **Indention:** 2 spaces


### Vim settings
  * **Python:**
    ```
     foldmethod=indent tabstop=4 expandtab
     let g:syntastic_python_flake8_args='--ignore=E501'
    ```
  * **HTML/CSS:**
    ```
    foldmethod=indent noexpandtab
    ```
  * **YAML:**
    ```
     foldmethod=indent tabstop=2 expandtab
    ```
  * **Markdown:**
    ```
     foldmethod=indent tabstop=2 expandtab
    ```

### Emacs settings
  * **General:**
    ```
     (setq require-final-newline t)
    ```
  * **Python:**
    ```
     (add-hook 'python-mode-hook
          (lambda ()
            (setq indent-tabs-mode nil)
            (setq python-indent-offset 4)
            (setq flycheck-flake8-args '("--ignore=E501"))))
    ```
  * **HTML/CSS:**
    ```
     (add-hook 'html-mode-hook (lambda () (setq indent-tabs-mode t)))
     (add-hook 'css-mode-hook (lambda () (setq indent-tabs-mode t)))
    ```
  * **YAML:**
    ```
     (add-hook 'yaml-mode-hook
          (lambda ()
            (setq indent-tabs-mode nil)
            (setq yaml-indent-offset 2)))
    ```
  * **Markdown:**
    ```
     (add-hook 'markdown-mode-hook
          (lambda ()
            (setq indent-tabs-mode nil)))
    ```

**Note**: A `.dir-locals.el` file is included so Emacs uses the correct settings when you open any file in this project.

## Git pull-request

### Contribute

1. Always amend or interactive rebase and force push changes (don't add adjustment commits on top).
2. Try to limit the number of commits and prefer to use a single commit for small changes.
3. Never do merge commits, rebase the master into your branch to update it.
4. Never use the `Update branch` feature on GitHub (create a merge commit)
5. Always add a single component before the commit message where the change belongs to (look at the history for inspiration)
6. If there is a matching open issue, reference it like `Fixes #1` in the extended commit message

### Review

1. Don't be too conservative if you see any potential problem (that's not blaming)
2. Find a logical and objective consensus
3. Never skip a review just because there are already approvals (more is better)

### Apply

1. Always wait for at least **2** approvals (possibly more, especially for huger changes)
2. Never apply when there is any disapproval left, always try to find a consensus
3. Use the "rebase and merge" feature or consider using "squash and merge" if too much noisy commits were added
