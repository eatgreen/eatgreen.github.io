[up vote]( "This answer is useful")[down vote]( "This answer is not useful")accepted

The issue is with statements of the sort `std::string str = 0;`. This leads to undefined behaviour.