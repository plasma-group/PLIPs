# PLIPs
Plasma Improvement Proposals (PLIPs) specify standards for implementations of the [plasma framework]. We've largely based the PLIP process off of Ethereum's [EIP process].

## Contributing
We've tried to design the PLIP process to be as open and accessible as possible. Everyone is welcome (and encouraged!) to create or review PLIPs. If you find any part of the PLIP process difficult to understand, please let us know by [creating an issue]. We're always trying to improve the PLIP process.

Respect, appreciation, and inclusivity are critical to building a truly open and accessible financial system. Contributors are expected to read through our [Contributing Guide] before contributing. 

### Creating a PLIP
Creating your own PLIP only takes a few quick steps:

1. Review [PLIP-1].
2. Write your PLIP using [this template].
3. Fork this repository (by clicking the "fork" button on the top right of this page).
4. Add your PLIP to your fork of the repository.
5. Submit a [Pull Request] from your fork to this repository.

Once you've completed these steps, we'll start getting your PLIP ready for review! A few things will happen next:

1. Our bot will make sure that your PLIP is correctly formatted. You'll be alerted if your PLIP has any formatting issues and you'll have a chance to fix those issues.
2. Once any formatting issues have been fixed, an editor will assign your PLIP a number and merge it into the main branch for further review.
3. Finally, our bot will automatically create a discussion/review issue for your PLIP.

Your PLIP will start out in the **DRAFT** phase. During this phase, you'll be able to quickly iterate on the PLIP. You're free to keep your PLIP in the **DRAFT** phase for as long as you'd like. 

Note that our bot will automatically merge Pull Requests to a PLIP from any of the PLIP's authors, as long as the PLIP is still in the **DRAFT** phase. Please ensure that a GitHub username is included for each PLIP author who wants to be able to edit the PLIP.

Once you believe your PLIP is ready to move out of the **DRAFT** phase, submit a Pull Request changing the status of your PLIP to **LAST CALL**. This signifies that your PLIP is ready for review by a wider audience.

Your PLIP will remain in the **LAST CALL** phase for a period of at least two weeks. Others will take this time to review your PLIP and request technical changes. If your PLIP was been in **LAST CALL** for at least two weeks and all requested changes have been addressed, the status of your PLIP can be changed to **FINAL**.

PLIPs marked as **FINAL** are considered part of the "Plasma Standard" - if you've reached this point, congratulations!

### Reviewing a PLIP
We need your help! PLIPs are only as good as the feedback they receive. Reviewing a PLIP is as easy as leaving a comment on the PLIP's [Pull Request].

## PLIP Statuses
- **DRAFT**: PLIP is undergoing rapid iteration and changes and is not ready for widespread review.
- **LAST CALL**: PLIP is mature and ready for review from a wider audience.
- **FINAL**: PLIP has been in **LAST CALL** for at least two weeks and any requested technical changes have been addressed.

## Credit
We're extremely thankful to the maintainers of Ethereum's [EIP repository]. Most of the PLIP format and process comes directly from the EIP repository.


[plasma framework]: https://plasma.io
[EIP process]: https://github.com/ethereum/EIPs
[EIP repository]: https://github.com/ethereum/EIPs
[this template]: ./PLIPs/PLIP-x.md
[Pull Request]: https://github.com/plasma-group/PLIPs/pulls
[creating an issue]: https://github.com/plasma-group/PLIPs/issues/new
[Contributing Guide]: http://docs.plasma.group/en/latest/src/reference/contributing.html
