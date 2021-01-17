---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# The Mythical Man-Machine

Welcome The Mythical Man-Machine.

**Robot learning** is a research field at the intersection of [machine learning](https://en.wikipedia.org/wiki/Machine_learning) and [robotics](https://en.wikipedia.org/wiki/Robotics). It studies techniques allowing a robot to acquire novel skills or adapt to its environment through learning algorithms. The embodiment of the robot, situated in a physical embedding, provides at the same time specific difficulties (e.g. high-dimensionality, real time constraints for collecting data and learning) and opportunities for guiding the learning process (e.g. sensorimotor synergies, motor primitives).

Example of skills that are targeted by learning algorithms include sensorimotor skills such as locomotion, grasping, active [object categorization](https://en.wikipedia.org/wiki/Object_recognition), as well as interactive skills such as joint manipulation of an object with a human peer, and linguistic skills such as the grounded and situated [meaning of human language](https://en.wikipedia.org/wiki/Natural-language_understanding). Learning can happen either through autonomous self-exploration or through guidance from a human teacher, like for example in robot learning by imitation.

Robot learning can be closely related to [adaptive control](https://en.wikipedia.org/wiki/Adaptive_control), [reinforcement learning](https://en.wikipedia.org/wiki/Reinforcement_learning) as well as [developmental robotics](https://en.wikipedia.org/wiki/Developmental_robotics) which considers the problem of autonomous lifelong acquisition of repertoires of skills. While [machine learning](https://en.wikipedia.org/wiki/Machine_learning) is frequently used by [computer vision](https://en.wikipedia.org/wiki/Computer_vision) algorithms employed in the context of robotics, these applications are usually not referred to as "robot learning".

# Usage of Slate

**Running Slate** can be conducted in to two ways:

1. Server Mode (the MD processed for development)

   ```shell
   bundle exec middleman server
   ```

2. Build Mode (just generate html files)

   ```shell
   bundle exec middleman build
   ```

The docs will be depolyed at [http://localhost:4567](http://localhost:4567/)

**Deploy the Stalte on Github**

1. Make sure you're working on a fork in your own account, not our original repo: `git remote show origin`.

2. Commit your changes to the markdown source: `git commit -a -m "Update index.md"`

3. Push the *markdown source* changes to GitHub: `git push`

4. Run `./deploy.sh`

   ```shell
   cd ~/slate/source
   git add index.html.md
   git commit -a -m "Update index.md"
   git push
   ../deploy.sh
   ```

   



**Markdown Syntax**

* Header (Note that only level 1 and 2 headers will appear in the table of contents.)

```markdown
# Level 1 Header
## Level 2 Header
### Level 3 Header
```

* Paragraph Text (Make sure the lines above and below your paragraph are empty.)



* Code Samples

```Python
print("this is a code sample")
```



* Code Annotation

> This code annotation

* Formatted Text

```markdown
This text is **bold**, this is *italic*, this is an `inline code block`.
```

* Links

```Markdown
This is an [internal link](#error-code-definitions), this is an [external link](http://google.com).
```

* Notes & Warnings

```html
<aside class="notice">
    You must replace meowmeowmeow with your personal API key.
</aside>
```

Use `class="notice"` for blue notes, `class="warning"` for red warnings, and `class="success"` for green notes.

<aside class="notice">
    You must replace meowmeowmeow with your personal API key.
</aside>

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

