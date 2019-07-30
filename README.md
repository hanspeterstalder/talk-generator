# Talk Powerpoint Generator
[![CircleCI](https://circleci.com/gh/korymath/talk-generator.svg?style=svg&circle-token=dcba7d5a9ff7953cff0526e201990c0b811b3aae)](https://circleci.com/gh/korymath/talk-generator)
[![codecov](https://codecov.io/gh/korymath/talk-generator/branch/master/graph/badge.svg?token=gqkCyuXop0)](https://codecov.io/gh/korymath/talk-generator)
[![License](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/korymath/britbot/blob/master/LICENSE.md)

## Description

Software to automatically generate talks, presentations for PowerPoint and/or Keynote. Their main purpose is for the improvisational comedy format "Improvised TED talk", where the actors have to present an unseen presentation. This software can be extended to be used for any sort of presentation including Pecha Kucha, Powerpoint Kareoke, etc.

## Demo

For a demo of this generator, please visit [talkgenerator.com](http://talkgenerator.com/), a platform created by [Shaun Farrugia](https://github.com/h0h0h0) to give easier access to this talk generator.

### Example

![Automatically Generated](https://media.giphy.com/media/8gWRbelmFyKoHfwz2Z/giphy.gif)]

## Easy Install and Run

Our program relies on certain APIs that require authentication in order to use it. Create a file named `.env` (don't forget the period) in your project directory. See the [wiki](https://github.com/korymath/talk-generator/wiki/Setting-Up-API-Keys) for details.

```sh
source setup.sh
talkgenerator --topic 'peanuts' --num_slides 10
# cd talkgenerator
# python run.py --topic 'cat' --num_slides 10
```

### Run arguments

| Argument               | Description               |
| ---------------------- | ------------------------- |
| `topic` | The topic of the generator. This works best if it is a common, well-known noun |
| `num_slides` | The number of slides in the generated presentation (*default: 10*) |
| `schema` | The presentation schema to use when generating the presentation. Currently, only two modes are implemented, being `default` and `test` (for testing during development) |
| `presenter` | The name that will be present on the first slide. Leave blank for an automatically generated name |
| `output_folder` | The folder to output the generated presentations (*default: `./output/`*) |
| `save_ppt` | If this flag is true(*default*), the generated powerpoint will be saved on the computer in the `output_folder`|
| `open_ppt` | If this flag is true (*default*), the generated powerpoint will automatically open after generating|
| `parallel` | If this flag is true (*default*), the generator will generate all slides in parallel |

## Running the generator as a microservice

Run the generator as a microservice at 0.0.0.0:5687.

`sh python run_web.py`

You can then hit `http://0.0.0.0:5687?topic=sometopic`. This will kick the main.py off.

## Program structure

See the [wiki](https://github.com/korymath/talk-generator/wiki/Program-structure) to know more about the inner implementation.

## Tests
Test files are `tests/*.py`, prefixed with `test_`. Test files use the `unittest` module.
They can easily be run all together when using PyCharm by right clicking on `talk-generator` and pressing *Run 'Unittests in talk-generator'*

```sh
. venv/bin/activate
pytest --cov=talkgenerator tests/
```

Test coverage is automatically handled by `codecov`. Tests are automatically run with CircleCI based on the `.yml` file in the `.circleci` directory.

## Credits

This ``Talk Generator`` is made by [Kory Mathewson](https://github.com/korymath)
and [Thomas Winters](https://github.com/TWinters),
with help from [Shaun Farrugia](https://github.com/h0h0h0), [Piotr Mirowski](https://github.com/piotrmirowski) and [Julian Faid](https://github.com/jfaid).

If you would like to refer to this project in academic work, please cite the following paper:

Winters T., Mathewson K.W. (2019) **Automatically Generating Engaging Presentation Slide Decks**. In: Ekárt A., Liapis A., Castro Pena M. (eds) Computational Intelligence in Music, Sound, Art and Design. EvoMUSART 2019. Lecture Notes in Computer Science, vol 11453. Springer, Cham

```
@InProceedings{winters2019tedric,
    author="Winters, Thomas
    and Mathewson, Kory W.",
    editor="Ek{\'a}rt, Anik{\'o}
    and Liapis, Antonios
    and Castro Pena, Mar{\'i}a Luz",
    title="Automatically Generating Engaging Presentation Slide Decks",
    booktitle="Computational Intelligence in Music, Sound, Art and Design",
    year="2019",
    publisher="Springer International Publishing",
    address="Cham",
    pages="127--141",
    isbn="978-3-030-16667-0"
}
```

## License

MIT License. Copyright (c) 2018 [Kory Mathewson](https://github.com/korymath), [Thomas Winters](https://github.com/TWinters), and [Shaun Farrugia](https://github.com/h0h0h0).
