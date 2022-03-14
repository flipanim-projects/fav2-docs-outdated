# Modal Class

Welcome to the Modal class documentation for FlipAnim.

This documentation is mostly just for me to help keep things straight (also for an easy reference. words are easier to read than code)

## Modal()

Initialize a modal with `new Modal()`.

| Parameter    | Description                          | Default value                          |
| ------------ | ------------------------------------ | -------------------------------------- |
| modalOptions | The options for the modal. Required. | [ModalOptions](#modaloptions) (object) |

## ModalOptions

The options for the modal.

| Parameter     | Description                                           | Default value                          |
| ------------- | ----------------------------------------------------- | -------------------------------------- |
| `title`       | Modal title. The main heading                         | String                                 |
| `description` | Modal description. Extra text shown below the heading | String                                 |
| `actions`     | Actions such as buttons, input fields, and more.      | [ModalActions](#modalactions) (object) |

## ModalActions

The actions for the modal, such as buttons and input fields.

| Parameter | Description        | Expected value                                    |
| --------- | ------------------ | ------------------------------------------------- |
| `buttons` | Modal buttons      | Array of [ModalButtonAction](#modalbuttonaction)s |
| `fields`  | Modal input fields | Array of [ModalInputAction](#modalinputaction)s   |

## ModalButtonAction

A button object.

| Parameter | Description                                   | Expected value                                  |
| --------- | --------------------------------------------- | ----------------------------------------------- |
| `text`    | Button text                                   | String                                          |
| `type`    | Type of button                                | [ModalButtonActionType](#modalbuttonactiontype) |
| `action`  | Action emitted when user clicks on the button | Function                                        |

## ModalInputAction

An input field object.

| Parameter     | Description         | Expected value |
| ------------- | ------------------- | -------------- |
| `placeholder` | Input placeholder   | String         |
| `value?`      | Input default value | String         |
| `id`          | Input ID            | String         |

## ModalButtonActionType

Type of the modal button.

| Option      | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| `cancel`    | Less highlighted button, useful for cancel buttons          |
| `dangerous` | "Dangerous" button, highlighted bright red to get attention |
