I have made the changes in the code so it allows user to retrive their registered name using their wallet address. It 
The line of code I have added for it are
const getMyName = async () => {
  try {
    if (!contract || !currentAccount) return;
    const name = await contract.getName(currentAccount);
    alert(`Your name is: ${name}`);
  } catch (error) {
    console.error("Error retrieving name:", error);
  }
};

and or the button
{/* ✅ Button to get registered name */}
  <button onClick={getMyName}>Get My Registered Name</button>


I also made changes which can show the currently connected Ethereum wallet address by the following line of code

//STEP 3: MAIN APP
<h2>Welcome, {name}</h2>
<p>Account: {account}</p>  // <-- This line displays the connected wallet address
What it does is 
account is a state variable (useState('')) that gets set when the wallet connects:

const address = await signer.getAddress();
setAccount(address);

