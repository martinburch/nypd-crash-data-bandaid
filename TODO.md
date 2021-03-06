Interested in hacking on crashmapper and/or the nypd crash data bandaid?  These
are some outstanding tasks:

### Low-hanging fruit

* Mobile block, to advise people against trying to load the map on their cell
  phones.
* A clearer disclaimer/link to licensing info.
* Determine end date from loaded data instead of hardcoding it.

### Bug-fixes

* __(RESOLVED)__ `b6c787bfe1a078039f67b9e1846f47684eb215aa`
  *Investigate GH issue #1, and see whether the Excel input script is sometimes
  dropping certain stats from intersections.*
* Memory profile and fix leaks, particularly in FF.

### Significant new features

* Allowing the selection of a date range, aggregating stats within.
* Providing an interface to view the vehicle type and contributing factor
  overlays.  The data's already loaded in.
* Display a color-coded legend.
* Location box to quickly jump to a specific address.
* Allow custom aggregation based off of a drawn shape.
  - Provide some useful pre-made shapes (council districts, CDs, boroughs,
    etc.)
* Allow automatic zoom-to-area.

### Infrastructural changes

* Tests (!)
* Implement staging server and nonbreaking push of new features from it.
* Change crashmapper JS namespace from `Letsmap` to `Crashmapper`.
* Possibly refactor crashmapper entirely out of the band-aid (dependencies are
  limited to the data transfer.)
* Investigate ways to break the data set into several requests while keeping it
  responsive.
  - Perhaps load the lon/lat data as an array alongside a simple array of the
    currently displayed overlay?  Two smaller requests instead of one, still
    provides immediate zoom/time scan response.  A third request could be
    point-in-time for all data dimensions, for providing readout on popup.

### Horizon

* Mobile support.
* Other cities.
* Complementary data sets (traffic counts, NYS collision data.)
