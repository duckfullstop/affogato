![Logo.svg](docs/img/Logo.svg)

_Just the kick your repair café craves._

> [!WARNING]
> _affogato_ is being **heavily developed**, and is **not yet ready for use**.
> If you would like to help out by contributing code or steering the project, please feel free to reach out!

## Supporters

_affogato_'s development is kindly supported by the _Ringwood Repair Café_.

# What is affogato?

_affogato_ will be a platform for managing the day-to-day operations of your Repair Café entirely paperlessly.

To give you a taste, some of the features we're planning include:

* Automatic synchronisation with ticketing platform for pre-registration and checkin (starting with pretix, potentially
  expanding)
* Trace the lifecycle of a repair from the moment it's pre-registered to its eventual resolution
* Monitor items taken home by repairers to complete
* Ensure safety test compliance, if applicable to the item
* Full localisation support (English first) for any region that can get use from it

# Free, Open Source Software

_affogato_ will always remain a fully open-source project, in the spirit of the Repair Café mission. You're free to run
it
yourself, though if you lack the infrastructure or know-how you will be able to use Hosted affogato.

Please see [the license](LICENSE.md) for more information.

## Hosted affogato

For those who don't wish to run an affogato instance for their own café, I intend to offer a hosted affogato service to
registered Café's for a nominal donation (I'm doing this in my spare time!).

More details on this once affogato is at a more mature stage.

---

# Technical Details

_affogato_ is being built as multiple components, that when combined produce the _affogato platform_.

## espresso

_espresso_ is _affogato_'s backend, and the brains of the operation.

It's being built as a Django 5 project, primarily chosen as Python is extremely straightforward for newcomers to
contribute to.

It will not have a frontend of its own, other than the Admin interface (for technical / debug work), and will host a
_GraphQL_ API for clients to talk to it.

## icecream

_icecream_ is _affogato_'s main control frontend, and the bit you actually interact with.

It will be built as a _React Router_ Single-Page Application, and it will be designed to operate on everything from
desktops, to laptops, to tablets, to mobile phones.

_icecream_ will have multiple views:

* the "front desk" view, for checking in customers and registering them if necessary
* the "manager" view, for moving customers (and their items) from the waiting area to a repairer, and then logging
  repair details
* the "safety" view, for completing compliance and safety information (such as PAT testing information) on items that
  require it
* the "oversight" view, for monitoring the state of the café and intervening when necessary
* the "administration" view, for printing paperwork, generating reports, and controlling other administrative functions
